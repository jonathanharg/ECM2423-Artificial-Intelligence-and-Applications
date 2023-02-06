# Local Search & Evolutionary Algorithms
###### Lecture 7 - 2023-02-06

## Optimisation Problem

A problem defined by a function that needs to be either minimised or maximised.

Types of problems
- Continuous: a continuous values
- Combinatorial: a combination of choices

Problem Difficulty
- Solvable analytically: calculus, linear algebra
- Solvable using mathematical optimisation: convex optimisation problem
- Unsolvable with traditional methods: multi-modal problems

## Local search algorithms

In many optimization problems, the path to the goal is irrelevant, the goal state itself is the solution.

In this case we can use a local search algorithms, keep a single "current" state and try to improve it.

> "Like climbing Everest in thick fog with amnesia"

**Problem** depending on the initial state, you can get stuck in a local maxima.

**Exploitation** only follow the best solutions. Mistakes/unoptimal solutions are not allowed.

**Exploration** incorrect solutions are allowed to explore the whole landscape.

## Simulated annealing search

Escape local maxima/minimum by allowing some "bad" moves but gradually decrease their frequency.

One can prove: If T decreases slowly enough, then simulated annealing search will find a global optimum with probability approaching 1

## Evolutionary Algorithm

An eveloutionary algorithm consists of several stochastic (random) processes. However it is not entirely random. Heritability of good traits and biased selection make the difference.

**Necessities**
- A way to represent solutions (phenotypes) as strings of symbols (genotypes)
- A (fitness) function that maps genotypes to phenotypes and maps phenotypes to a measure of 'fitness'
- Operators to reproduce and vary individual genotypes in such a away that inheritance of traits occurs.

The EA does not need to know the details of the fitness function (alghough it may help). The fitness function can be a black box.

**Crossover** randomised average of parents
**Mutation** small random permutation

### Travelling Salesman Problem

A solution is tour passing through all cities
- Represent tours as permutations: list of integers without repetitions (e.g., 25143 for a tour of 5 cities)
- Fitness (to minimise): the tour length
- Search operators:
- one-point crossover for permutations: part of the first parent is copied and the rest is taken in the same order as in the second parent
- swap mutation: two elements are swapped at random)
- the offspring is a VALID permutation

### Symbolic Regression

Find a curve that best fits given noisy data points

Candidate solutions are curves (ie. functions)
Fitness is the sum of errors at each data point.
Functions can be represented using a tree encoding.

Search Operators:
– Sub-tree swap crossover: swap two sub-trees in the parents
– Sub-tree mutation: replace a sub-tree with a randomly generated sub-tree
– The offspring is a VALID function

### Ant Controller

Candidate solutions: set of instructions (left, right, move, if-food-ahead, prog2, prog3)
- Fitness (to maximise): food eaten
- Control programs can be represented as trees
- Mutation and Crossover acting on trees

## Application Areas
- Planning: Routing, Scheduling, Packing
- Design: Electronic Circuits, Neural Networks, Structure Design
- Simulation: Model economic interactions of competing firms in a market
- Identification: Fit a function to medical data to predict future values
- Control: Design a controller for gas turbine engine, design control system for mobile robots
- Classification: Game playing, Diagnosis of heart disease, Detecting SPAM
