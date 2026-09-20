# Maze Search: DFS, IDS & A*

A Python maze solver that compares three graph-search strategies on the same grid environment:

- Depth-First Search (DFS)
- Iterative Deepening Search (IDS)
- A* Search with Manhattan-distance heuristic

The solver reads a text-based maze, searches from the start node to the goal, reports explored-state counts and path cost, and can render the resulting path as an image.

## How it works

Each maze is represented as a grid containing:

- `A` - start
- `B` - goal
- spaces - traversable cells
- other characters - walls

The implementation provides separate frontier structures for stack-based and priority-based search, tracks explored states, reconstructs the final path through parent references, and visualises the solution.

## Algorithms

### DFS

Uses a stack frontier and explores deeply before backtracking.

### IDS

Runs repeated depth-limited searches with increasing limits until a solution is found.

### A*

Uses:

```text
f(n) = g(n) + h(n)
```

where `g(n)` is path cost and `h(n)` is Manhattan distance to the goal.

## Run

From `maze_src/`:

```bash
python maze.py maze3.txt --algo DFS
python maze.py maze3.txt --algo IDS
python maze.py maze3.txt --algo "A*"
```

The solver prints the path as directional moves, reports the number of states explored, and writes a visualisation to `maze.png`.

## Stack

- Python
- graph search
- priority queues
- heuristic search
- Pillow image rendering
