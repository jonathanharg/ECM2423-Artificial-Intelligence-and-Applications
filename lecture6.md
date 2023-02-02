# Heuristic Search
###### Lecture 6 - 2023-02-01

**Uninformed (Blind) Search** only has the knowledge provided in the search problem.

**Informed (Heuristic) Search** uses problem specific knowledge to pick which node to expand. Typically involves a heuristic function $h(n)$ estimating the cheapest path from $n.State$ to the goal state.

## Best-First Search
Use an evaluation function f to estimate the desirability of each node.

Algorithm:
1. Put start node in the fringe and compute its f
2. Exmapnd the most desirable node in the fringe
3. Update the fringe and compute f for the new nodes
4. Until goal node not in fringe go to 2

Spcial cases:
- Greedy search
- A-star

## Properties of Greedy Search
**Greedy Search is not optimal**

It often gets good results but not optimal ones.

- **Complete** No - can get stuck in loops
- **Time** $O(b^m)$ but a good heuristic $h$ can give dramatic improvement
- **Space** $O(b^m)$ keeps all nodes in memory
- **Optimal** No

## A* Search
Idea: include cost of reaching node

Evaluation function $f(n)=g(n)+h(n)$

Where $g(n)$ is the cost of reaching $n$, $h(n)$ estimated cost of reaching goal from state of $n$. $f(n)$ estimated cost of the cheapest path to a goal state that goes through path of $n$.

A* will be optimal when $h(n)$ underestimates the cost of reaching a goal, A* is optimal.

### Admissible Heuristics
A heuristic is admissible if for every node $n$, $h(n)\le h^\star(n)$ is the minimum cost to reach the goal state from $n$

An admissible heuristic *never overestimates* the cost to reach teh goal, it is *optimistic*.

### Properties of A*
- **Complete** Yes, unless there are infinitely many nodes with $f(n)\le C^\star$
- **Time** Exponential in solution length, unless $h$ is very accurate $|h(n) - h^\star(n)| \le O(\log h^\star(n))$
- **Space** Keeps all nodes in memory
- **Optimal** Yes, if $h$ is admissible

### Relaxed Problems
If the rules of a slide puzzle were relaxed so that a tile can move anywhere, then $h_1(n)$ gives an optimal solution.

If the rules are relaxed so that a tile can move to any adjacent square, then $h_2(n)$ gives an optimal solution.

Heuristics can be measured against IDS (iterative deepening search) to determine their efficiency.

