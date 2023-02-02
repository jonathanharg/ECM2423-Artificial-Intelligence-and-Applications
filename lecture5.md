# Problem Solving as Search
###### Lecture 5 - 2023-01-30

## Problem
You can often represent a problem as a graph. We can then solve the problem by searching a corresponding graph.

**State space** is represented by a directed graph
**Nodes** are problem situations
**Edges** are actions or legal moves

The problem is the combination of a state space, a start and a goal condition.

*Note: there may be several nodes which satisfy the goal condition*

### Optimisation Problems

**Optimisation** minimise the cost of a solution.

We need to assign costs to edges. Therefore the cost of the solution is the cost of the solution path.

## Search Methods

- **Uninformed techniques** systematically search complete graph, unguided.
- **Informed methods** use problem specific information to guide search in promising directions.

### Evaluation of Serach Strategies
- **completeness** does it always find a solution if one exists?
- **time complexity** number of nodes generated
- **space complexity** maximum number of nodes in memory
- **optimality** does it always find a least-cost solution?

### Uninformed Search
- Depth-first search
- Breadth-first serach
- Iterative deepening
- Bi-directional search

#### Depth-First Search
- **Completeness** NO, susceptible to infinite loops (check for cycles)
- **Time complexity** HIGH time complexity as in the worst case it visits all states
- **Space complexity** LOW as it only remembers one path at each time
- **Optimality** NO, not guaranteed to find shortest solution first

TODO: Iterative Deepening Search

#### Breadth-First Search
- **Completeness** YES
- **Time Complexity** HIGH time complexity as in the worst case it visits all states.
- **Space Complexity** HIGH as it remembers all paths
- **Optimality** YES

TODO: include time & space complexity slides


