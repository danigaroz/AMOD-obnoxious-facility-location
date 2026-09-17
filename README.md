# Obnoxious Facility Location — A Computational Study

An empirical study of the **Minimum-Impact Location Problem** (Church & Cohon, 1976),
implemented in Python with PuLP and CBC, evaluated on 60 randomly generated instances
covering three orders of magnitude in problem size.

## TL;DR

- **Problem:** where to place *p* undesirable facilities among *m* candidate sites so that
  the population within their impact radius `S` is minimised.
- **Approach:** implement the ILP, solve with CBC, compare against a greedy heuristic,
  and characterise how the difficulty depends on the covering density.
- **Main finding:** the difficulty of the problem is not driven by size but by the impact
  radius. A sharp difficulty cliff appears at `S ≈ 10`; below it, the solver is unbeatable;
  above it, the greedy heuristic becomes competitive in both speed and solution quality.

## Highlights

- End-to-end pipeline: instance generator → LP relaxation → MILP → heuristic → analysis.
- 60 instances, 6 size classes, two experimental studies (scalability and sensitivity).
- All results reproducible from fixed random seeds.
- Report and slides written in LaTeX.

## Tech stack

- **Language:** Python 3
- **Modelling:** [PuLP](https://github.com/coin-or/pulp)
- **Solver:** [CBC](https://github.com/coin-or/Cbc) (open-source MILP)
- **Data & plotting:** NumPy, pandas, matplotlib
- **Environment:** Google Colab (free tier)
- **Docs:** LaTeX (article + Beamer/metropolis)

## Repository contents

| File | Description |
|:---|:---|
| `AMOD_project_MILP.ipynb` | Reproducible Colab notebook — all code and results |
| `AMOD_report.pdf` | Written report (12 pages) |
| `AMOD_slides.pdf` | Presentation slides |
| `main.tex`, `refs.bib`, `slides.tex` | LaTeX sources |
| `results_*.csv` | Raw experimental data |
| `fig_*.png` | Figures used in the report and slides |

## How to reproduce

Open `AMOD_project_MILP.ipynb` in Google Colab and run all cells.
Every reported number is deterministic given the fixed seeds.

## Context

Final project for *Algoritmi e Modelli per l'Ottimizzazione Discreta* (AMOD),
Università degli Studi di Roma Tor Vergata, A.A. 2025–26.
Starting reference: Church & Drezner, *Review of obnoxious facilities location problems*,
Computers & Operations Research 138:105468 (2022).

## Note on the use of AI

The Python implementation was developed with AI-assisted coding. All modelling choices,
experimental design, interpretation of results and written content are the author's own
work. See report Section 3.4 for details.

## Author

**Daniel Garoz Vazquez** — [danigv1605@gmail.com](mailto:danigv1605@gmail.com)
