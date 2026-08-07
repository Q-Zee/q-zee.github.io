---
title: Wolf, Goat & Cabbage
parent: Models
nav_order: 2
permalink: /models/wolf-goat-cabbage/
---

# Solving the Wolf, Goat and Cabbage riddle
*by Mario Guzzi — QuzziCode@gmail.com*

{: .note }
> This is the clearest teaching example on the site — start here if you want to see the CQM approach on a problem you can hold in your head before looking at the airline model.

## The riddle

> A farmer buys a wolf, a goat, and a cabbage at the market. On the way home he reaches a river and rents a boat, but the boat only carries the farmer plus **one** item at a time.
>
> Left alone, the wolf eats the goat, or the goat eats the cabbage.
>
> How does the farmer get everyone across intact? — [full riddle on Wikipedia](https://en.wikipedia.org/wiki/Wolf,_goat_and_cabbage_problem)

## Solving it with the quantum computer

We want the quantum computer to figure out the sequence of moves **without any hints from us on how to solve it.** All we provide is: the physically possible moves, the situations to avoid, and a way to measure that the goal is reached efficiently.

## Method: D-Wave CQM Hybrid Solver

### Variables

Four binary variables represent where each object is:

- Wolf, Goat, Cabbage, Farmer — each `0` = left bank, `1` = right bank
- Each variable is tracked across every step (boat trip), forming a grid of variables × steps
- Two extra sets of binary variables track which items are *available* to move on a given step, and which one is *chosen*

### The state diagram

![Diagram of the farmer, wolf, goat and cabbage crossing the river by boat, one trip at a time](/assets/images/gcw-diagram.svg)

The solver works out a full sequence of trips like this one:

1. Bring the goat to the other side
2. Return empty
3. Bring the cabbage to the other side
4. Return with the goat
5. Bring the wolf to the other side
6. Return empty
7. Bring the goat to the other side — **solved**

### Constraints

1. The initial step has all 4 items on the left bank.
2. The farmer alternates banks every trip.
3. "Available" items are those on the bank where the farmer currently is.
4. A "choice" must be 0 or 1 items, and only from what's available. (The farmer may travel empty.)
5. Between consecutive steps, state must transition consistently with the chosen item: removed from the source bank, added to the destination bank.
6. The wolf and goat, or the goat and cabbage, may never be left together on a bank without the farmer.

### Objective function

Without an objective, the farmer could take infinite valid trips and never actually finish. The objective simply rewards having as few items as possible on the left bank, summed over all steps — which pushes the solver toward the shortest valid sequence:

$$
\text{minimize} \sum_{\text{steps } t} \left(\text{items remaining on left bank at step } t\right)
$$

{: .important }
> The constraints describe only what moves are *physically possible* — never *how* to solve the puzzle. The solver finds the strategy on its own. This is the core demonstration of what quantum annealing brings to combinatorial problems: describe the rules and the goal, not the algorithm.

## Code

- [Jupyter notebook version](https://github.com/Q-Zee/DWave) (set your D-Wave API token before running)
- [Python script version](https://github.com/Q-Zee/DWave) (`GCW` folder)
- [Run directly in D-Wave Leap IDE](https://ide.dwavesys.io/#https://github.com/q-zee/DWave)
