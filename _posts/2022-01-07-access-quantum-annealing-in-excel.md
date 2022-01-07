---
layout: post
title: Access Quantum Computing from Excel
---

# Accessing Quantum Computing from Excel

So much software resources are available for experimenting with Quantum Computing, whether using Gate models or Quantum Annealers. 
There is much support using the Python language and many use Jupyter and Google colab Notebooks to quickly elaborate models and test.

A major interest with using Quantum Annealing is for solving hard problems and many use Excel spreadsheets everyday to solve complex problems, manually or by using solver plugins.

I have recently contributed to connecting a [Java web app](https://www.vyoupoint.com/) to Python code (which is widely used for running Quantum models) for integrating a Quantum Computing solver prototype for the [airline crew trip problem](https://q-zee.github.io/DWave/Quzzi/docs/usage).
It was a natural progression to want to connect such Python code to Excel to put Quantum Computing at the reach of regular folks solving everyday business "puzzles".

I needed a good example everyone could understand, where Quantum Annealing can be used and results presented on a spreadsheet. I chose to go with the [N-Queens puzzle](https://q-zee.github.io/DWave/8Queens/) before takling something more substancial, such as forecasting crew member requirements to fly a commercial airline schedule.

# Discovering xlwings

I have discovered [xlwings](https://www.xlwings.org/) which allows doing exactly that. 
It provides two important features I needed: 

* Ability for a python program to read from a spreadsheet with similar methods as what one uses in VBA (Visual Basic for Applications).
* Ability to define and call Python function that one can call as an Excel "=Function()". 

# Prototype

As a way to get my feet wet with a prototype, I adapted the solver for the [N-Queens problem](https://q-zee.github.io/DWave/8Queens/) to be callable from Excel and created a Benchmark solver spreadsheet to demonstrate using Quantum Annealing to solve this problem and render results in Excel.

A video of the end result from the [QuzziCode YouTube channel](https://www.youtube.com/channel/UCddYU5elbTFC5F6YZv-4Otw) can be found [here](https://www.youtube.com/watch?v=xMIqiaroMrk&t=222s)

Enjoy and subscribe to the channel for more videos like this!






