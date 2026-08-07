---
title: What is Quantum Annealing?
nav_order: 2
permalink: /what-is-quantum-annealing/
---

# What is Quantum Annealing?

{: .note }
> You do **not** need a physics background to use this technology or to read this page. Quantum Annealing solvers are coded using ordinary math and Python — the physics happens inside the hardware.

## The short version

Quantum Annealing (QA) is a way of finding good solutions to large "combination" problems — problems where there are countless choices to make, and each choice affects the cost or feasibility of every other choice. Crew scheduling, vehicle routing, and shift assignment are classic examples: these are [NP-hard optimization problems](https://en.wikipedia.org/wiki/NP-hardness), meaning the number of possible solutions explodes far faster than any classical computer can check them all.

## Classical vs. quantum: an analogy

- 🚶‍♀️ **Classical computing** *tells* the computer **how** to solve a problem, step by step. It's like walking through a labyrinth turn by turn until you find the exit — you might get exhausted before you find it, or never find it at all within your time budget.

- 💥 **Quantum Annealing** *shows* the computer what a good answer looks like, using a quality-rating function, and lets it explore many paths through the labyrinth simultaneously. The paths that lead to exits naturally rank at the top of the list of candidate solutions.

## How a problem gets to the quantum computer: QUBO

To run on a quantum annealer, a problem is expressed as a **QUBO** — a Quadratic Unconstrained Binary Optimization. In plain terms: every decision in the problem becomes a variable that can be `0` or `1` (yes/no), and the "goodness" of any complete set of decisions is scored by a single equation:

$$
\text{minimize} \quad \sum_i c_i x_i + \sum_{i<j} c_{ij} x_i x_j
$$

where each $x_i \in \{0, 1\}$ is a yes/no decision, and the $c_i$, $c_{ij}$ terms are the costs and interactions between decisions that the solver is trying to minimize. The annealer's job is simply to find the combination of 0s and 1s that makes this expression as small as possible.

D-Wave provides two ways to build this:

| Model | What it is | Trade-off |
|---|---|---|
| **BQM** (Binary Quadratic Model) | The raw QUBO form above — you write the cost/interaction terms directly. | Full control, but constraints (e.g. "the farmer can only carry one item") must be hand-encoded into the equation, which is easy to get wrong on complex problems. |
| **CQM** (Constrained Quadratic Model) | A higher-level model where constraints are written as ordinary mathematical expressions (e.g. `x + y <= 1`), and D-Wave converts them to the QUBO form automatically. | Much easier and less error-prone to build correctly; the trade-off happens under the hood instead of in your code. |

Every model on this site is available in one or both forms — see the [Models](/models/) section for worked examples, including a full worked example with the Wolf, Goat and Cabbage riddle.

## Why this matters for airline scheduling

Airline crew and fleet scheduling problems have exactly this shape: many interacting yes/no decisions (which crew member on which flight, which aircraft on which route) with cost and legality constraints tying them together. Classical solvers "walk the labyrinth" using heuristics that have to be carefully tuned per problem and still run out of time budget on hard cases. Quantum Annealing offers a different lever on the same problem — see [Airline Crew Trip](/models/airline-crew-trip/) for the real-world prototype.
