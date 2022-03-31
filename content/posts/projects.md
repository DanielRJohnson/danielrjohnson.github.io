---
title: "Projects"
date: 2022-03-04T22:33:41-06:00
draft: false
---

 >Quick note: This is a collection of some of my bigger, more impressive, and fun projects. 
 >To see complete code and information about all of my projects, check out 
 >[my GitHub](https://github.com/danielrjohnson). 

---
## Glimmer ✨

### Description and Motivation
[Glimmer](https://github.com/DanielRJohnson/Glimmer) is my own programming language. Cool, right? I decided to do this because I really enjoyed my programming language semantics course and wanted to dive deeper. To do this, I read the book [Writing An Interpreter In Go by Thorsten Ball](https://interpreterbook.com/), followed along with what they did, and have been adding much on top of it.

### What is in the repo?
Specifically, this repo implements a lexer, parser, typechecker, and a tree-walking evaluator for my language with a complete file-runner, REPL (Read-Eval-Print-Loop), RPPL(Read-Parse-Print-Loop), and RLPL (Read-Lex-Print-Loop).

### What can it do?
The goal of Glimmer is to have a language with clean syntax that is capable in semantics and performance. 

Glimmer supports:
 - Common arithmetic/logical operations
 - Non-basic types with operations and builtin functions (strings, arrays, dictionaries)
 - Variable binding
 - First-class functions
 - Static scoping
 - Static typing
 - Loops
 - Recursion
 - etc.

### Example

```
>> inc = fn(x: int) -> int { x + 1 }
>> applyTwice = fn(f: fn(int) -> int, x: int) -> int { f(f(x)) }
>> applyTwice(inc, 1)
3
>> fact = fn(n: int) -> int { ife n == 0 { 1 } else { fact(n - 1) * n } }
>> fact(5)
120
```

This example shows how first class functions work in `Glimmer`. For many more details and examples, check out the repo.

---
## MOBIUS 🐋

### Description and Motivation
[MOBIUS](https://github.com/DanielRJohnson/MOBIUS) stands for "MObile keystroke Inferencing Using Sensors" (academic security research is known for reaching acronyms). The goal and main deliverable of MOBIUS is a Recurrent Neural Network that takes in time series gyroscope and accelerometer data from a mobile device and tries to predict which keys were pressed in a given time period. 

The motivation behind this is to explore why physical sensor data should be a dangerous permission on mobile operating systems. Essentially, what can an attacker do if they have their hands on this data from your phone through a siphoning app? As it turns out, they might be able to get your passwords and other critical information.

### What is in the repo?
The repo holds our data collection server, scripts to process that data into machine-recognizable arrays, notebooks to train our models, and plots to visualize the whole process. 

### Report
This was a course project for EECS 700, a graduate course on mobile security at KU. I had one partner and we came up with this idea and implementation on our own. We submitted a final research paper, which can be found [here](https://github.com/DanielRJohnson/MOBIUS/blob/main/EECS_700__Mobile_Security_Final_Report.pdf).

### TL;DR Results
![keyboard character activities](/MOBIUS-accuracies.png)

This is a diagram that shows the percent accuracy that we could correctly predict which key was pressed at a given point. The overall accuracy was about 70%, which is very promising because our model was not giant or trained for a very long time. This is an on-going area of research and I'm excited to see where it goes. For more info, check out the report.

---
## DJ-Learn 🧠

### Description and Motivation
[DJ-Learn](https://github.com/DanielRJohnson/DJ-Learn) is my own from-scratch machine learning library. Machine learning is one of my biggest passions, and I sometimes dislike how abstracted it is from the math. Most of the times this is a blessing, but when you try to actually learn ML algorithms it is a good idea to implement them from scratch (up to a certain difficulty). That being said, this is my place to implement ML models from scratch and play around with the algorithms that I am learning.

### What is in the repo?
At the time of writing this (3/11/22), I currently have decision trees, linear and logistic regression, naive bayes, K nearest neighbors, and a simple feed-forward neural network implemented. If I choose to dig into more algorithms in the future, more will show up in the repo.

### Example
![Linear Regression Example](/gradient.png)

This is a diagram that shows the descent of a cost function using linear regression, essentially better fitting of a dataset algorithmically and iteratively using a machine learning model. I pulled this image from a [workshop I gave for KUAI](https://github.com/DanielRJohnson/AIO-Gradient-Descent-Workshop) where I reused a lot of my linear regression code.

---
## Visualizing-Shortest-Path ⚡

### Description and Motivation
[Visualizing-Shortest-Path](https://github.com/DanielRJohnson/Visualizing-Shortest-Path) is a simple website I made that allows you to visualize path-finding algorithms by placing walls on a 2D grid. You can watch the algorithm run and it's pretty visually satisfying. This project near and dear to my heart because it most likely got me my first internship and it was my first ever dive into web technologies. Learning path-finding algorithms was a cherry on the top. 

### What is in the repo?
The repo holds all of the code for this frontend-only app as well as some example images. This app is also being hosted by GitHub pages meaning that you can play with it [here](https://danielrjohnson.github.io/Visualizing-Shortest-Path/).

### Example
![Visualizing Shortest Path Example](/visexample.gif)

This is a gif example run of me creating a maze and running the A* path-finding algorithm on it. Since it is a gif, it is less smooth than the real deal, but you get the idea.

---
## Ultrasonic-Pong 🔊

### Description and Motivation
[Ultrasonic-Pong](https://github.com/DanielRJohnson/Ultrasonic-Pong) is a project that takes sensor input data from an HC_SR04 ultrasonic sensor and makes a game of Pong out of it. Ultrasonic sensors measure distance by emitting and receiving sounds outside of our hearing range. I correlated that distance to the height of a paddle in Pong. With this, I connected two of them to a Raspberry Pi (which was a harder electrical task then I thought) to round out the functionality.

### What is in the repo?
The repo contains the logic and library integration for the Pong game as well as the integration for the ultrasonic sensor. The code is only ~150 lines, and the bulk of the project was learning GPIO electrical communications.

### Example
[This](https://www.youtube.com/watch?v=lfq0VmZCbaI) is a demo video of me running the game. It was a janky setup, but I enjoyed it.

---
## Py2Folders 📂

### Description and Motivation
[Py2Folders](https://github.com/DanielRJohnson/Py2Folders) is a bit of an enigma. [Folders](https://danieltemkin.com/Esolangs/Folders/) is an [Esoteric Programming Language](https://esolangs.org/wiki/Esoteric_programming_language) made by [Daniel Temkin](https://danieltemkin.com/) where the instructions are represented completely by the structure of folders. That is, there are NO FILES. The names of the folders and any files within are COMPLETELY IGNORED. I found this very fascinating. So, I made Py2Folders: a partial-transpiler from a subset of Python to Folders.

### What is in the repo?
The entire implementation of the transpiler in in the repo from the Python abstract syntax tree object encoding to the folder emission. There is also information on what subset of Python is permitted and some examples packaged with.

### Example
The following is the folders "code" transpiled from the Python statement `print("h")`

```
py_tests/print_h/
└── 0 - F_PRINT
    ├── 00printdecl
    │   ├── 0
    │   ├── 1
    │   ├── 2
    │   └── 3
    └── 01printexpr
        ├── 00litdecl
        │   ├── 0
        │   ├── 1
        │   ├── 2
        │   ├── 3
        │   └── 4
        ├── 01littype
        │   ├── 0
        │   └── 1
        └── 02litvalue
            └── 0h
                ├── hexchar0
                │   ├── 0
                │   ├── 1
                │   │   └── 1
                │   ├── 2
                │   │   └── 1
                │   └── 3
                └── hexchar1
                    ├── 4
                    │   └── 1
                    ├── 5
                    ├── 6
                    └── 7

31 directories, 0 files
```

The structure of the folders indicates what operations happen. For instance, 4 folders indicates that we are creating a print statement and the next folder should be the expression to be printed. Remember, the names of the folders are not taken into consideration, the names listed are just for debugging purposes. Then, 5 folders means that our expression is a literal, 2 folders means that the literal is a character, and the subsequent folders is a hexidecimal representation of the character 'h' in ASCII. All of this together, the Folders interpreter will print the character 'h'. It is rare for something to be so interesting, disgusting, and beautiful at the same time.

##### If you have read this far, thank you and have a good day! 🙂