# searching-.......
# Uninformed Search Algorithms: BFS, DFS & UCS
### Case Study: 8-Puzzle Problem

> Part of the **AI Learning Roadmap** — Problem Solving by Search track
> Author: Kajal Singh, Assistant Professor

---

## 📁 Repo Structure

```
uninformed-search-8puzzle/
├── README.md              ← this file (overview + theory summary)
├── code/
│   └── search_8puzzle.py  ← BFS, DFS, UCS implementation
└── docs/
    ├── Lecture_Notes.pdf          ← full theory notes
    └── Code_Listing.pdf           ← annotated code listing
```

## 📌 Overview

This module covers the three foundational **uninformed search strategies** — Breadth-First Search (BFS), Depth-First Search (DFS), and Uniform Cost Search (UCS) — using the classic **8-puzzle** as a worked case study.

| Algorithm | Data Structure | Optimal? | Time Complexity | Space Complexity |
|---|---|---|---|---|
| BFS | Queue (FIFO) | ✅ Yes (unit cost) | O(b^d) | O(b^d) |
| DFS | Stack (LIFO) | ❌ No | O(b^m) | O(b·m) |
| UCS | Priority Queue | ✅ Yes (any non-neg. cost) | O(b^(1+⌊C*/ε⌋)) | Same order |

*b = branching factor, d = solution depth, m = max search depth, C* = optimal cost, ε = min edge cost*

## 🧩 Problem Setup

- **State:** 3×3 grid, tiles 1–8 + blank (0)
- **Goal:** `1 2 3 / 4 5 6 / 7 8 0`
- **Actions:** slide blank Up / Down / Left / Right
- **State space size:** 181,440 reachable states (half of 9! — solvability depends on inversion parity)

## 🔑 Key Insight

When all move costs are equal (as in this puzzle), **UCS behaves identically to BFS** — both guarantee the shortest path. DFS trades that optimality guarantee for drastically lower memory use (linear vs. exponential in depth).

## 🐍 Quick Start

```bash
python code/search_8puzzle.py
```

**Sample output:**
```
BFS  -> Path length: 2 moves | Nodes expanded: 5
DFS  -> Path length: 6 moves | Nodes expanded: 9
UCS  -> Path length: 2 moves | Cost: 2 | Nodes expanded: 5
```

## 📊 Project / Assignment

Run all three algorithms across scramble depths (5, 10, 15, 20 moves) and log nodes expanded, path length, runtime, and peak frontier size. Full instructions and results template are in `docs/Lecture_Notes.pdf` (Section 10).

## 📚 Full Materials

- **[Lecture_Notes.pdf](docs/Lecture_Notes.pdf)** — theory, hand-traced example, architecture diagram, advantages/disadvantages, interview questions, research directions
- **[Code_Listing.pdf](docs/Code_Listing.pdf)** — fully commented Python implementation with complexity analysis per function

## ➡️ Next Topic

**Topic 6: Knowledge Representation and Reasoning** *(queued)*
*(Bridge note: this topic's exponential blow-up on deep 8-puzzle instances is exactly what motivates moving to heuristic search — A*, IDA* — already covered in Topic 5.)*
