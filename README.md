![Github Sponsorship](img/Logo-Small.png)
# Welcome to Quzzi

This repository hosts experimental code which uses [Quantum Annealing (QA)](https://en.wikipedia.org/wiki/Quantum_annealing) to solve [np-hard optimization problems](https://en.wikipedia.org/wiki/NP-hardness). The author is using the [DWave Quantum Hybrid Solver](https://cloud.dwavesys.com/leap/signup/) as well as [Simulated Annealing (SA)](https://en.wikipedia.org/wiki/Simulated_annealing) for this purpose.

The main interest is with solving **real-world** use cases within the **airline industry**. Code for the original functional prototype for solving Crew Trip problems is included in the code repository. 

Also included in the code repository are various side problems that can help understand how to use this new technology. Solvers are implemented using Quadratic Unconstrained Binary Optimization ([QUBO](https://support.dwavesys.com/hc/en-us/articles/360003684474-What-is-a-QUBO-)) using the DWave [BQM](https://support.dwavesys.com/hc/en-us/articles/360009944734-What-is-a-Binary-Quadratic-Model-BQM-) and [CQM](https://support.dwavesys.com/hc/en-us/articles/4410049190807-New-Hybrid-Solver-Constrained-Quadratic-Model).

The code is provided as an Apache 2 Open Source license.

## Blog

You can find the Quzzi blog [here](https://q-zee.github.io/blog).

## Quick Start

### Overview

>[Examples overview](https://q-zee.github.io/DWave/)

### Jump to specific solvers

>[Airline Crew Trips: Quzzi library](https://q-zee.github.io/DWave/Quzzi/)

>[Strategy Problem: Solving Goat/Wolf/Cabbage riddle](https://q-zee.github.io/DWave/GCW)

>[Viable Configurations: Solving 8 Queens problem with BQM and CQM](https://q-zee.github.io/DWave/8Queens)

### Load code in Leap IDE

>[Load models in your D-Wave Leap Account](https://ide.dwavesys.io/#https://github.com/q-zee/DWave)

### Sponsors!
[![Github Sponsorship](img/sponsorqzee2.png)](https://github.com/sponsors/Q-Zee)

## Catalyst ✈
The author's initial drive behind this work was to prove that Quantum Annealing could be used to solve certain hard problems that airlines of various sizes are confronted with on a daily basis. Despite using powerful classical computing solvers used by the larger airlines, these systems continue to struggle to find optimum results within operational deadlines, especially in a world where strategies are in constant increasing flux.

## Classical computing challenges
Having personally written and deployed classical solvers for some of these problems, the author's experience with the constant battle to work around the inpractibility of brute force solvers and "right sizing" heuristic algorithms to obtain viable operational results for np-hard problems made him wish for a "chip" that would handle the combinatorics and solution landscape exploration. 

## Experimental code
Discovering the existance of the DWave Quantum Annealing technology in 2018, it appeared as a wish come true and he engaged in learning about and experimenting with Quantum computing in general, but more specifically how to use the DWave Quantum Computer to attempt solving the Airline Crew Trip use case. 

## Why consider a Quantum Annealer for optimization?

Quantum Annealing allows finding solutions to large combination problems that are hard to solve with classical computing and offers opportunities for breakthoughs in both speed and solution quality. Furthermore, to code solvers using such a Quantum computer does not require knowledge of physics (although it helps understand why it works). 

Problems where there are countless "choices" to be made with consequences on cost/time as these choices interact with each other to form even greater combinations, there is an opportunity to use QA to find the best fit solutions where Classical computing can fail rooted in problem magnitude and time to solution constraints.

## What is the difference between Classical and Quantum Annealing solvers?

Here is a simplistic analogy from the author's point of view: 

- 🚶‍♀️ One **tells** a classical computer **"how"** to solve a problem by **telling it the steps** (code) needed to construct a solution. It is like walking through a labyrinth until the exit is found. You might get exhausted before the end and never find the exit.

- 💥 The Quantum Annealer **"knows"** how to solve the problem by using a **quality rating function** one gives it (code) to compare its solutions. The paths to the labyrinth _"manifest"_ themselves and the ones leading to exits rank at the top of the list of possible solutions.

## What to expect from the Quzzi site

Quzzi aims at making Quantum Annealing solvers more accessible and as simple as possible to anyone by sharing its own experience, through code, examples and training on methodologies.

Quzzi will be listening to anyone interested in this work and more specifically what they wish to learn from it.

[![Github Sponsorship](img/sponsorqzee2.png)](https://github.com/sponsors/Q-Zee)

Sponsor Quzzi today and get involved to get it to work for you!

<!---
Q-Zee/Q-Zee is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
