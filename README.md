♛ Solving N-Queens Problem: Exhaustive Search vs. Genetic Algorithm
A comprehensive comparative study of optimization algorithms on constraint satisfaction problems

Python Status Version

📋 Overview
This project presents a rigorous comparative analysis of four optimization algorithms for solving the N-Queens problem—a fundamental challenge in constraint satisfaction where the objective is to place N queens on an N×N chessboard such that no two queens attack each other (no shared row, column, or diagonal).

The study evaluates algorithm performance across scales from N=10 to N=500, examining real-world trade-offs between execution time, memory usage, and solution reliability.

🎯 Algorithms Evaluated
#	Algorithm	Approach	Complexity
1	Depth-First Search	Exhaustive backtracking	O(N!)
2	Greedy Hill-Climbing	Local optimization	O(N²) per iteration
3	Simulated Annealing	Probabilistic search	Adaptive
4	Genetic Algorithm	Population-based evolution	Adaptive
📊 Key Performance Comparison
Performance Table
Algorithm	Best For	Practical Limit	Speed @ N=500	Status
DFS	N ≤ 20	N = 30 (142.5s)	❌ Timeout	Impractical
Greedy	N ≤ 100	N = 500 (586s)	⚠️ Risky	Fast but unstable
SA	N ≤ 500	N = 500 (469s)	✅ 8 minutes	Recommended
GA	N = 500	N = 500 (6521s)	✅ ~2 hours	Reliable
Critical Insights
✨ Key Finding: Exhaustive search fails exponentially, while metaheuristics scale effectively

🔴 DFS Fails at N=50+ — Exponential growth makes it impractical beyond N=30
🟢 Metaheuristics Succeed at Scale — SA and GA reliably solve N=500
💾 Memory is Abundant — All methods use <1MB even for N=500
⏱️ Time is the Bottleneck — CPU execution time determines algorithm choice

📁 Project Structure
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
    
The N-Queens problem at large scales (N=500) is only solvable with metaheuristic approaches—a critical lesson for developing real scheduling systems, routing optimization, and resource allocation algorithms in production environments.

Version 1.0 | Last Updated: May 2026

For detailed methodology and complete results, see reports/ directory.
