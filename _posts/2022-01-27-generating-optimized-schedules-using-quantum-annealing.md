---
layout: post
title: Generating optimized schedules using Quantum Annealing
---

# Generating optimized schedules using Quantum Annealing

## Demonstration

I have published a video demonstrating the use of Quantum Annealing for generating an optimized schedule forecast to determine if an airline has enough staff to cover a flight schedule. You can find it [here](https://youtu.be/WsJiS56SQ74) with other videos on this [channel](https://www.youtube.com/channel/UCddYU5elbTFC5F6YZv-4Otw).

As for a previous project, I am using Excel with xlwings calling python code to setup the Quantum Annealing problem using the DWave Quantum Computer.

## Use case: airline schedule feasibility

Assigning airline crew members to the flights they operate is a multi-step process. Each step is its own puzzle with competing constraints which must be delivered by a hard (and legal) deadline. 

Therefore, failure to produce results is not an option. 
It often becomes a matter of compromise to accept the best (or least costly) solution.

When an airline creates or changes a flight schedule to best address their market, it is not truly known how many crew members will be needed. 

Why? Because it is not just a matter of calculating a ratio of hours of work vs crew member availability. The flights must be sequenced in a way that fits the flight duty regulations, safety buffers and assignments must also respect the work rules in a given period.

A small change in a flight schedule may cause sequences to no longer fit the constraints, and a higher cost solution may need to be accepted.

It becomes a problem similar to fitting a number of boxes of various sizes in a building with various sizes rooms each with their own restrictions. No box can be left behind and the least number of rooms need to be used.

Those are difficult combination problems which the final solution can inflate the number of crew members needed by a non-trivial number. A lot of efforts is then required to figure out how to best build the trips and then get the best fit in the monthly plan.

Being able to estimate an accurate number of crew members prior to actually building final trips and monthly plans can help prepare to address new challenges imposed by a new flight schedule to determine if existing staff is sufficient to fly the schedule. 

If not, new trained hires may be required. Since it costs and can take months to hire and train new crew members, early visibility of the crew count for operating a given schedule can be key.

These challenges are perfectly suited for solvers that deal with large combinations such as Quantum Annealers.

## The example

The example is based on a real life case of a startup airline with 2 A-320 aircraft. This is a small number of aircraft but even so can offer its own challenges.

The question posed is: How many crew sets (Captain, First officer and Cabin attendants) are needed to fly a schedule to determine if the current employee count is sufficient or if changes need to be planned.

In the example, the trips are given from the crew trip solver (using the code published [here](https://q-zee.github.io/DWave/Quzzi/)). The focus is on creating feasible schedules allocating all the trips respecting a few work rules.

There are 3 trips per day with variying weekly frequency (operating day of week). We also have 2 standby periods (one AM and one PM) for a total of 5 tasks per day for part 1 of the demonstration and 8 tasks per day in part 2.

The rules considered here are:

	1 - A maximum of 6 consecutive work days are allowed
	2 - There must be a minimum number of days off for each crew sets
	3 - Each trip must be followed by 12 hours of rest (a simplified version of actual rest rules)
	4 - A day off is only counted as a day off if the entire 24 hour period (local) is free from duty

The goal:

	1 - Respect all the constraints above (rules)
	2 - Minimize the number of crew sets needed
	
## Using the Quantum Annealer from DWave

### Model used 

To solve this problem we chose to use the Constrained Quadratic Model (CQM), the latest model from DWave (at the time of this writting).

We chose the CQM over the Binary Quadratic Model (BQM) for its simplicity in expressing constraints. We have used the BQM model for solving the crew trip problem which feeds the schedules for this problem.

The decision variables (the quantum binary variables if you will) are defined as follows: 

	Task {i} assigned to crew set {s} on day {d}
  
  If the variable is 1 the task i is assigned to set s on day d otherwise it is not.

We estimate the number of crew sets excluding combination restrictions considering the number of days off needed and add some slack to allow flexibility with the model which the solver aims at minimizing.

### Constraints and Objective

#### Constraints

Two "common sense" structural constraints are needed:

1 - Any given item can only be assigned to 1 crew set at a time (no double coverage)
2 - All items must be assigned on any given day

Then comes the work rules described earlier with the addition of a special constraint to deal with multiple day trips (see the T4 task in the example which is followed by an "x". The constraint essentially says that the "x" must always follow where the "T4" item goes, they can't be apart from each other.

#### Objectives

There are two parts in the objective:

1 - "Pump" as many tasks as possible onto the crew sets at the top of the list as opposed to the bottom ones. 
2 - Penalize items that conflict with each other (overlap or breaks the rest rule between pairs).

### Python Code excerpt

Here is a sample for the "common sense" constraints mentioned previously

    # 1 - Any item on any given day can only be assigned to at most one person

    for d in range(self.ND):
      for i in range(len(items[d])):
        self.cqm.add_constraint( sum( self.board[s][i][d] for s in range(self.NS) ) <= 1, label=f"asg_per_person_d_{d}_i_{i}" )

    # 2 - All items must be assigned on any given day
    for d in range(self.ND):
      self.cqm.add_constraint( sum( self.board[s][i][d] for s in range(self.NS) for i in range(len(items[d])) ) == len(items[d]), label=f"all_assigned_d_{d}" )

Legend:
```
	s is a crew set
	d is a relative day in the period
	i is a task item
```
## Excel, desktop and solver

We use Excel and Python running on a Intel(R) Core(TM) i5-8250U CPU @ 1.60GHz 1.80 GHz Window laptop, to prepare the problem for the Quantum Computer and calling the DWave CQM Hybrid Solver to solve it.

You can find more details about DWave and running your own models [on DWave Leap](https://cloud.dwavesys.com/leap/login/?next=/leap/) and how to connect Excel to Python at [xlwings.org](https://www.xlwings.org/).

