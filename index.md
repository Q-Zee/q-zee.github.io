---
title: Home
layout: home
nav_order: 1
description: "Quzzi — Quantum Annealing Optimization Coding"
permalink: /
---

# Quzzi
{: .fs-9 }

Quantum Annealing for hard real-world optimization problems in aviation.
{: .fs-6 .fw-300 }

[Explore the models](/models/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[What is Quantum Annealing?](/what-is-quantum-annealing/){: .btn .fs-5 .mb-4 .mb-md-0 }

---

{: .note }
> Presented at **[Conference name]**, [date]. This site is the reference material for the aviation prototypes shown there — code, models, and explanations all live here.

## What this is

This site hosts experimental code that uses [Quantum Annealing (QA)](https://en.wikipedia.org/wiki/Quantum_annealing) to solve [NP-hard optimization problems](https://en.wikipedia.org/wiki/NP-hardness), using the D-Wave Quantum Hybrid Solver as well as classical Simulated Annealing (SA) for comparison.

The main interest is solving **real-world** use cases in the **airline industry** — code for the original functional prototype solving the Crew Trip problem is included in the code repository, alongside smaller demonstration problems that make the technology easier to learn.

Solvers are implemented using Quadratic Unconstrained Binary Optimization ([QUBO](https://support.dwavesys.com/hc/en-us/articles/360003684474-What-is-a-QUBO-)), via D-Wave's [BQM](https://support.dwavesys.com/hc/en-us/articles/360009944734-What-is-a-Binary-Quadratic-Model-BQM-) and [CQM](https://support.dwavesys.com/hc/en-us/articles/4410049190807-New-Hybrid-Solver-Constrained-Quadratic-Model) formulations. All code is Apache 2.0 open source.

## Why quantum annealing for airline scheduling?

Airlines already run powerful classical solvers, and those solvers still struggle to hit optimum results within operational deadlines — especially as schedules change constantly. Quantum Annealing offers a different approach to the same combinatorial problem: instead of *telling* the computer the steps to build a solution, you *describe* what a good solution looks like and let the solver search the whole landscape at once. See [What is Quantum Annealing?](/what-is-quantum-annealing/) for the full explanation, no physics background required.

## Get started

- [Browse the models →](/models/)
- [Read the blog →](/blog/)
- [View the code on GitHub →](https://github.com/Q-Zee/DWave)
- [Load code directly in D-Wave's Leap IDE →](https://ide.dwavesys.io/#https://github.com/q-zee/DWave)

[![Github Sponsorship](/img/sponsorqzee2.png)](https://github.com/sponsors/Q-Zee)

Sponsor Quzzi today and get involved.
