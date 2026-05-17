# N-Queens Problem Solver

Comparing different algorithms to solve the N-Queens problem. Tests exhaustive search, greedy, simulated annealing, and genetic algorithms on boards from N=10 to N=500.

## Algorithms

1. **DFS (Depth-First Search)** - Tries every possibility. Fast for small boards, times out at N=50+
2. **Greedy** - Makes quick local choices. Very fast but sometimes fails
3. **Simulated Annealing** - Random search with cooling. Balanced approach
4. **Genetic Algorithm** - Population-based. Most reliable but slowest

## Quick Results

| Algorithm | Best For | Speed |
|-----------|----------|-------|
| DFS | Small (N ≤ 20) | ✅ Fast |
| Greedy | Medium (N ≤ 100) | ✅ Very Fast |
| Simulated Annealing | Large (N ≤ 500) | ⚠️ 8 mins |
| Genetic Algorithm | Large (N ≤ 500) | ⏱️ 2 hours |

## Project Structure

```
N-Queens-Problem/
├── src/
│   ├── dfs.py
│   ├── greedy.py
│   ├── simulating.py
│   └── genetic_algorithm.py
├── docs/
│   └── diagrams and images
└── reports/
    └── performance results
```

## Key Finding

Brute force methods break at large scales. For N=500, you need metaheuristics like simulated annealing or genetic algorithms.

## License

MIT