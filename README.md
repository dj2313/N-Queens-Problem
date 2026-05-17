# ♛ Solving N-Queens Problem: Exhaustive Search vs. Genetic Algorithm

<div align="center">

**A comprehensive comparative study of optimization algorithms on constraint satisfaction problems**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen.svg)](.)
[![Version](https://img.shields.io/badge/Version-1.0-blue.svg)](.)

</div>

---

## 📋 Overview

This project presents a **rigorous comparative analysis** of four optimization algorithms for solving the N-Queens problem—a fundamental challenge in constraint satisfaction where the objective is to place N queens on an N×N chessboard such that no two queens attack each other (no shared row, column, or diagonal).

The study evaluates algorithm performance across scales from **N=10 to N=500**, examining real-world trade-offs between execution time, memory usage, and solution reliability.

---

## 🎯 Algorithms Evaluated

| # | Algorithm | Approach | Complexity |
|---|-----------|----------|-----------|
| 1 | **Depth-First Search** | Exhaustive backtracking | O(N!) |
| 2 | **Greedy Hill-Climbing** | Local optimization | O(N²) per iteration |
| 3 | **Simulated Annealing** | Probabilistic search | Adaptive |
| 4 | **Genetic Algorithm** | Population-based evolution | Adaptive |

---

## 📊 Key Performance Comparison

### Performance Table

| Algorithm | Best For | Practical Limit | Speed @ N=500 | Status |
|:--------:|:--------:|:--------:|:--------:|:--------:|
| **DFS** | N ≤ 20 | N = 30 (142.5s) | ❌ Timeout | Impractical |
| **Greedy** | N ≤ 100 | N = 500 (586s) | ⚠️ Risky | Fast but unstable |
| **SA** | N ≤ 500 | N = 500 (469s) | ✅ 8 minutes | Recommended |
| **GA** | N = 500 | N = 500 (6521s) | ✅ ~2 hours | Reliable |

### Critical Insights

> ✨ **Key Finding:** Exhaustive search fails exponentially, while metaheuristics scale effectively
>
> - 🔴 **DFS Fails at N=50+** — Exponential growth makes it impractical beyond N=30
> - 🟢 **Metaheuristics Succeed at Scale** — SA and GA reliably solve N=500
> - 💾 **Memory is Abundant** — All methods use <1MB even for N=500  
> - ⏱️ **Time is the Bottleneck** — CPU execution time determines algorithm choice

---

## 📁 Project Structure

```
N-Queens-Problem/
│
├── 📄 README.md                          # Project documentation
│
├── src/                                  # Algorithm implementations
│   ├── dfs.py                            # Depth-First Search
│   ├── greedy.py                         # Greedy Hill-Climbing
│   ├── simulating.py                     # Simulated Annealing
│   └── genetic_algorithm.py              # Genetic Algorithm
│
├── docs/                                 # Reference materials
│   ├── diagrams/
│   │   └── N-Queens.drawio               # Problem visualization
│   └── images/
│       ├── empty.png                     # Initial state
│       ├── dfs_10.png                    # Valid solution (N=10)
│       └── simulated-annealing.png       # Algorithm comparison
│
└── reports/                              # Experimental results
    ├── plot_time.pdf                     # Execution time analysis
    ├── plot_memory.pdf                   # Memory usage analysis
    ├── plot_accuracy.pdf                 # Solution quality metrics
    └── N-Queens-drawio.pdf               # Full analysis document
```

---

## 🚀 Algorithm Selection Guide

### For Real-World Applications

| Use Case | Recommended | Reason |
|----------|------------|--------|
| **Small boards (N ≤ 20)** | DFS | Guaranteed optimal solution, fast |
| **Medium boards (N = 50-200)** | Greedy or SA | Good speed-quality balance |
| **Large boards (N ≥ 500)** | Simulated Annealing | Best speed-reliability trade-off |
| **Critical accuracy needed** | Genetic Algorithm | Highest solution quality |
| **Real-time systems** | Greedy | Fastest (but risky on hard instances) |

### Decision Tree

```
Is N ≤ 20?
  ├─ YES → Use DFS (guaranteed, fast)
  └─ NO → Is real-time required?
         ├─ YES → Use Greedy (fastest)
         └─ NO → Is solution quality critical?
                ├─ YES → Use GA (most reliable)
                └─ NO → Use SA (best balance)
```

---

## 💡 Key Findings

### 1️⃣ Deterministic Methods Hit a Wall
- DFS reliably solves up to **N=30** in seconds
- Beyond N=30, execution time explodes (>2 minutes)
- At N=50, DFS times out completely

### 2️⃣ Metaheuristics Enable Scaling
- Simulated Annealing solves N=500 in **~8 minutes**
- Genetic Algorithm solves N=500 in **~2 hours**
- Both consistently find valid solutions

### 3️⃣ Hardware Constraints Matter More Than Theory
- Memory usage plateaus at <1MB for all algorithms
- CPU time, not memory, is the limiting factor
- Real-world performance differs from Big-O complexity

### 4️⃣ Speed vs. Reliability Trade-off
- **Fastest:** Greedy (586s @ N=500) — but can fail
- **Recommended:** Simulated Annealing (469s @ N=500) — reliable balance
- **Most Reliable:** Genetic Algorithm (6521s @ N=500) — guaranteed success

---

## 🎓 Educational Value

This project demonstrates fundamental principles applicable to real-world problems:

- ✅ **Scalability limits** of different algorithmic paradigms
- ✅ **Hardware-software interaction** in algorithm selection
- ✅ **Trade-offs** between optimality, speed, and reliability
- ✅ **Practical deployment** considerations for optimization systems
- ✅ **Metaheuristic strategies** for constraint satisfaction

---

## 🏆 Conclusion

**Traditional exhaustive search approaches fail at scale.** This study proves that as problem complexity grows, **intelligent heuristics consistently outperform brute-force methods**. 

The N-Queens problem at large scales (N=500) is only solvable with metaheuristic approaches—a critical lesson for developing real scheduling systems, routing optimization, and resource allocation algorithms in production environments.

---

<div align="center">

**Version 1.0** | Last Updated: May 2026

For detailed methodology and complete results, see `reports/` directory.

</div>
