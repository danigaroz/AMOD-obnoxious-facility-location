# Facility Location: CBC Solver vs Greedy Heuristic

[![Language](https://img.shields.io/badge/language-Python-blue)]()
[![Course](https://img.shields.io/badge/course-Discrete%20Optimization-red)]()

When does the greedy beat the solver? An empirical study of the **Minimum-Impact Location Problem** (Church & Cohon, 1976), implemented in Python with PuLP and CBC, benchmarked across 60 randomly generated instances covering three orders of magnitude in problem size.

**Author:** Daniel Garoz Vazquez · **Grade:** 30/30

---

## Problem

Where to place *p* undesirable facilities (landfills, power plants, prisons) among *m* candidate sites so that the population within their impact radius `S` is minimised? This is an NP-hard combinatorial optimisation problem with a MILP formulation solvable by exact solvers such as CBC, but also tractable by greedy heuristics. The question is: when does the heuristic become competitive?

## Key results

- **Difficulty is not driven by size but by the impact radius `S`.**
- **A sharp difficulty cliff appears at `S ≈ 10`:** below it, CBC is unbeatable in both speed and quality; above it, the greedy heuristic becomes competitive.
- **End-to-end pipeline:** instance generator → LP relaxation → MILP → greedy heuristic → gap analysis across 60 instances and 6 size classes.

## Methodology

| Step | Technique |
|---|---|
| Problem formulation | MILP (Mixed-Integer Linear Programming) |
| Solver | CBC via PuLP (open-source) |
| Heuristic | Greedy (iterative best-site selection) |
| Experimental design | 60 instances, 6 size classes, scalability + sensitivity studies |
| Analysis | Optimality gap, runtime comparison, covering density effect |
| Reproducibility | Fixed random seeds throughout |

## Tech stack

- **Language:** Python 3
- **Modelling:** PuLP
- **Solver:** CBC (COIN-OR)
- **Data & plotting:** NumPy, pandas, matplotlib
- **Environment:** Google Colab
- **Docs:** LaTeX (article + Beamer)

## Repository structure

```text
├── notebook.ipynb   Reproducible Colab notebook — all code and results
├── report.pdf       Written report (12 pages)
├── slides.pdf       Presentation slides
├── results_*.csv    Raw experimental data
└── fig_*.png        Figures used in the report and slides
```

## How to reproduce

Open `notebook.ipynb` in Google Colab and run all cells. Every reported number is deterministic given the fixed seeds.

## Note on the use of AI

The Python implementation was developed with AI-assisted coding. All modelling choices, experimental design, interpretation of results and written content are the author's own work. See report Section 3.4 for details.

## Context

Final project for *Algoritmi e Modelli per l'Ottimizzazione Discreta*, Università degli Studi di Roma Tor Vergata, A.A. 2025–26 (Erasmus exchange). Starting reference: Church & Drezner, *Review of obnoxious facilities location problems*, Computers & Operations Research 138:105468 (2022).
