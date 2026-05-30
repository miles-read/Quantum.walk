# Quantum "walk" maze solver:
---
A quantum algorithm that finds maze solutions using grover's search,
I've not seen an example online that works for a 4x4 maze so I'm currently trying to implement one here.


## Quick start
you need python 3.8 or later
Install packages
```sh
pip install qiskit qiskit-aer
```

run the included **jupyter notebook**

play around with finding new paths or including custom mazes

## How this works:
For any generated maze, If you want to walk n squares from the starting square there are 4^n different possible paths. Assuming that the end square of the maze is within this distance,

we can reduce the problem of solving a maze down into a search problem, where we search through these possible paths to find the ones that arrive at a correct solution.

We can use grover's algorithm here to check all possible paths simultaneously via superposition and then only amplify the paths that make it to the end without hitting a wall or going out of bounds.

This sounds relatively easy however the difficulty comes from the fact that the function that checks if you have reached the end of the maze without breaking any rules must be encoded using only quantum gates which are tricky to work with.


