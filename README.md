# Welcome to Q-Zee

This repository hosts experimental code which uses Quantum and Simulated annealing to solve optimization problems. 

The initial drive behind this work was for myself to prove that Quantum Annealing could be used to solve certain hard problems that airlines of various sizes are confronted with on a daily basis. The powerful classical computing solvers many airlines utilize continue to struggle to find optimum results within operational deadlines.

Having personally written and deployed classical solvers for some of these problems, the constant battle to work around the inpractibility of brute force solvers and "right sizing" heuristic algorithms to obtain "usable" results for np-hard problems made me wish for a "chip" that would handle the combinatorics and solution landscape exploration. 

Discovering the existance of the DWave Quantum Annealing technology in 2018, it appeared as a wish come true and I engaged in learning about Quantum computing in general but more specifically how to use the DWave Quantum Computer to attempt solving the Airline Crew Trip use case. A QUBO prototype for a minimalistic real-world use case (Quzzi) can be found here.

In the process of learning how to use the tool kit that drives the Quantum solvers, I practiced with a few toy problems, some of which are also included.

# Discovering Quantum Annealing

## Why use a Quantum Annealer for optimization?

Quantum Annealing allows finding solutions to large combination problems that are hard to solve with classical computing and offers opportunities for breakthoughs in both speed and solution quality. Furthermore, to code solvers using such a Quantum computer does not require knowledge of physics (although it helps understand why it works). 

Where there are multiple "choices" to be made with consequences on cost/time as these choices interact with each other ... there is an opportunity to use the QA to find the best fit solutions where Classical computing can fail.

## What is the difference between Classical and Quantum Annealing solvers?

Here is a simplistic analogy: 

- 🚶‍♀️ One **tells** a classical computer **"how"** to solve a problem by **telling it the steps** (code) needed to construct a solution. It is like walking through a labyrinth until the exit is found. You might get exhausted before the end and never find the exit.

- 💥 The Quantum Annealer **"knows"** how to solve the problem by using a **quality rating function** one gives it (code) to compare its solutions. The paths to the labyrinth _"manifest"_ themselves and the ones leading to exits rank at the top of the list of possible solutions.


<!---
Q-Zee/Q-Zee is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
