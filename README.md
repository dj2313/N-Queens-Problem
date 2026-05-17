# Solving N-Queens Problem: Exhaustive Search vs. Genetic Algorithm

## Project Overview

This project compares four different algorithms for solving the **N-Queens problem** — a classic constraint satisfaction challenge where the goal is to place N queens on an N×N chessboard such that no two queens attack each other (no shared row, column, or diagonal).

## What We're Testing

We evaluate the performance of four algorithms across board sizes ranging from **N=10 to N=500**:

1. **Depth-First Search (DFS)** — Exhaustive backtracking approach
2. **Greedy Hill-Climbing** — Local search that always takes the best move
3. **Simulated Annealing** — Probabilistic search that escapes local minima
4. **Genetic Algorithm** — Evolutionary approach using population-based search

## Key Findings

| Algorithm | Best For | Limit | Speed at N=500 |
|-----------|----------|-------|----------------|
| **DFS** | Small boards (N ≤ 30) | Times out after N=30 | Not feasible |
| **Greedy** | Fast solutions | N=500 with 586 seconds | Moderate, risky |
| **Simulated Annealing** | Reliable balance | N=500 with 469 seconds | Practical (~8 min) |
| **Genetic Algorithm** | Guaranteed solutions | N=500 with 6521 seconds | Slow but reliable |

## Critical Results

- **DFS fails at N=50+** — Exponential growth makes it impractical beyond N=30 (142.5 seconds)
- **Metaheuristics work at scale** — SA and GA solve N=500 successfully
- **Memory is not the bottleneck** — All methods use <1MB even for N=500
- **Execution time is the limiting factor** — Determines which algorithm to use

## Project Structure

```
src/                    # Python implementations
├── dfs.py              # Depth-First Search
├── greedy.py           # Greedy Hill-Climbing
├── simulating.py       # Simulated Annealing
└── genetic_algorithm.py # Genetic Algorithm

docs/                   # Documentation
├── diagrams/           # N-Queens problem visualization
└── images/             # Solution examples

reports/                # Results and analysis
├── plot_time.pdf       # Execution time comparison
├── plot_memory.pdf     # Memory usage comparison
└── plot_accuracy.pdf   # Solution quality comparison
```

## Main Takeaway

**For real-world systems:**
- Use **Simulated Annealing** for large N (best speed-reliability trade-off)
- Use **Genetic Algorithm** if solution quality is critical but time permits
- Avoid **DFS** for N > 20 in production environments
- **Hardware constraints matter more than theory** — memory is plentiful, but CPU time is limited

## Conclusion

This study proves that as problem complexity grows, **smart heuristics outperform brute-force exhaustive search**. The N-Queens problem at scale (N=500) is only solvable with metaheuristic approaches, not traditional backtracking—a lesson applicable to real scheduling, routing, and optimization problems in modern software systems.
