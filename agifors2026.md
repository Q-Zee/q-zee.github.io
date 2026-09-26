---
layout: default
title: AGIFORS Crew Management SG 2026 — Quzzi
permalink: /agifors2026/
robots: noindex, nofollow
---

<!-- Staged font-size trial for this page only. Not touching the
     shared theme yet - if this reads better, the plan is to promote
     these same values into the site-wide stylesheet. -->
<style>
.agifors-preview { font-size: 19px; line-height: 1.6; }
.agifors-preview h1 { font-size: 46px; }
.agifors-preview h3 { font-size: 26px; }
.agifors-preview h2 { font-size: 34px; }
.agifors-preview h4 { font-size: 22px; }
.agifors-preview p, .agifors-preview li { font-size: 19px; }
</style>
<div class="agifors-preview" markdown="1">

<p align="center"><img src="/assets/images/agifors2026-banner.jpg" alt="" style="max-width: 480px; width: 100%; height: auto; border-radius: 8px; margin: 0 auto 1.5rem; display: block;"></p>

# Airline crew planning meets quantum computing. No, really.
### AGIFORS Crew Management Study Group Meeting 2026

**When:** October 20–22, 2026 &nbsp;·&nbsp; **Where:** Vienna, Austria *(as of Sep 2026 — check the [official listing](https://agifors.org/crew_2026) for the current venue)*

This page is the reference material for the AGIFORS Crew Management SG 2026 session, presented by Mario Guzzi, co-founder of [VYouPointAero](https://www.vyoupoint.com).

## About this work

This session presents **Quzzi** — Mario's independent, open-source research into applying Quantum Annealing to airline optimization problems — specifically its Crew Trip solver, with Crew Assignment work also discussed. Quzzi is broader than just this work; it also includes smaller teaching examples that make the underlying approach easier to follow (see below).

A version of the Quzzi Trip solver has separately been implemented within the [VYouPointAero](https://www.vyoupoint.com) app, through a collaboration between the two.

## What you'll see in this session

Both **crew trip construction** and **crew-to-schedule assignment** are formulated as QUBO models (Quadratic Unconstrained Binary Optimization) and solved on real D-Wave quantum annealers — not a simulation. Hybrid solvers are benchmarked alongside for comparison. Realistic operating crew cost estimates can be derived directly from schedules, even before a full trip-and-assignment plan exists.

Quantum computing in airline crew planning has been a "someday" topic for years. This session — and this site — is about what's possible today.

## Explore the prototypes

- [Airline Crew Trip solver (Quzzi)](/DWave/Quzzi/) — real-world crew trip generation as a QUBO/BQM, the prototype discussed in this session
- [All Quzzi models](/DWave/) — the Trip solver above, plus two smaller teaching examples (Wolf-Goat-Cabbage, 8 Queens) that illustrate the same BQM/CQM approach on problems anyone can follow without an airline background
- [Full code repository](https://github.com/Q-Zee/DWave) (Apache 2.0)
- [Run the code yourself in D-Wave's Leap IDE](https://ide.dwavesys.io/#https://github.com/q-zee/DWave)

Crew Assignment is discussed in the session but isn't published as code here yet — only the Trip solver above is currently available.

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

</div>
