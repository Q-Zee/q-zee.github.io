---
layout: default
title: AGIFORS Crew Management SG 2026 — Quzzi
permalink: /agifors2026/
robots: noindex, nofollow
---

# Airline crew planning meets quantum computing. No, really.
### AGIFORS Crew Management Study Group Meeting 2026

**When:** October 20–22, 2026 &nbsp;·&nbsp; **Where:** Vienna, Austria *(as of Sep 2026 — check the [official listing](https://agifors.org/crew_2026) for the current venue)*

This page is the reference material for the AGIFORS Crew Management SG 2026 session, presented by Mario Guzzi, co-founder of [VYouPointAero](https://www.vyoupoint.com).

## About this work

This session presents **Quzzi** — Mario's independent, open-source research into applying Quantum Annealing to airline optimization problems — specifically its Crew Trip and Assignment solvers. Quzzi is broader than just this work; it also includes smaller teaching examples that make the underlying approach easier to follow (see below).

A version of the Quzzi Trip solver has separately been implemented within the [VYouPointAero](https://www.vyoupoint.com) app, through a collaboration between the two. That collaboration is mentioned here for context — the code, the research, and this presentation are Quzzi's.

## What you'll see in this session

Both **crew trip construction** and **crew-to-schedule assignment** are formulated as QUBO models (Quadratic Unconstrained Binary Optimization) and solved on real D-Wave quantum annealers — not a simulation. Hybrid solvers are benchmarked alongside for comparison. Realistic operating crew cost estimates can be derived directly from schedules, even before a full trip-and-assignment plan exists.

Quantum computing in airline crew planning has been a "someday" topic for years. This session — and this site — is about what's possible today.

## Explore the prototypes

- [Airline Crew Trip solver (Quzzi)](/DWave/Quzzi/) — real-world crew trip generation as a QUBO/BQM, the prototype discussed in this session
- [All Quzzi models](/DWave/) — the Trip solver above, plus two smaller teaching examples (Wolf-Goat-Cabbage, 8 Queens) that illustrate the same BQM/CQM approach on problems anyone can follow without an airline background
- [Full code repository](https://github.com/Q-Zee/DWave) (Apache 2.0)
- [Run the code yourself in D-Wave's Leap IDE](https://ide.dwavesys.io/#https://github.com/q-zee/DWave)

## Why quantum annealing, briefly

Classical solvers for crew planning are heuristic and time-boxed — they walk toward a solution step by step and can run out of time before finding a good one. A quantum annealer is instead given a way to *score* a candidate solution, and lets the physical system settle toward low-cost solutions on its own — using quantum effects to explore the landscape differently than step-by-step search, without being told the exact steps to follow. See the [homepage](/) for the fuller explanation, no physics background required.

## Resources

**Documents**
- [A QUBO Formulation for Flight-Trip Sequencing (PDF)](/papers/QUBO-Trip-Sequencing-Formulation.pdf) — the mathematical formulation behind the Trip solver, written for a technical/math audience. Companion to the [Python implementation](https://github.com/Q-Zee/DWave).

**Videos**
- *(to be added)*

## Support this work

Quzzi is independent, self-funded research. If this session showed you something worth continuing, you can back it directly through [GitHub Sponsors](https://github.com/sponsors/Q-Zee) — every bit helps it grow beyond the initial airline use case.

## Questions after the talk?

Reach out to Mario Guzzi, or to the AGIFORS Crew Management SG co-chairs: Marcel Sol (marcel.sol@agifors.org) or Philipp Reske (crew@agifors.org).
