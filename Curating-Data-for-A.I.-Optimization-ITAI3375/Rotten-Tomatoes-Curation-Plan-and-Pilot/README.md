# Rotten Tomatoes Curation Plan

**Course:** ITAI 3375 – Curating DATA for A.I. Optimization  
**Student:** Chloe Tu  
**Collaborator (Midterm):** Kaire Campomanes  
**Institution:** Houston City College — Applied AI & Robotics

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![pandas](https://img.shields.io/badge/library-pandas-150458.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![Kaggle](https://img.shields.io/badge/platform-Kaggle-20BEFF.svg)
![Data Curation](https://img.shields.io/badge/topic-Data_Curation-9cf.svg)
![CC0](https://img.shields.io/badge/license-CC0_1.0-lightgrey.svg)

---

## What this folder is

This folder holds the **Rotten Tomatoes** line of work for ITAI 3375: turning a messy public critic-review dataset into something an AI or analytics system can actually use.

| Subfolder | Status | Contents |
|-----------|--------|----------|
| **[Midterm/](./Midterm)** | Complete | Full curation plan, presentation, working pilot notebook, pilot outputs |
| **Final/** | Upcoming | Final project deliverables will be added here |

---

## Midterm (complete)

**Rotten Tomatoes Curation Plan and Pilot** — Team: Chloe Tu & Kaire Campomanes

| Fact | Detail |
|------|--------|
| Dataset | Rotten Tomatoes movies + critic reviews (Kaggle, stefanoleone992), CC0 1.0 |
| Scale | 17,712 movies · 1,130,017 critic reviews |
| Core problem | `review_score` in **814** distinct string forms; **27.1 %** missing |
| Pilot sample | 50,000 reviews (seeded, `random_state=42`) |
| Survival rate | **72.4 %** of rows survived normalization to 0–100 |
| Letter-grade failure | School mapping agreed with site Fresh/Rotten only **64.5 %** of the time — reported as a failure |
| Hand audit | 100 records; **47** had at least one problem |
| Duplicates found | 119,471 exact duplicate review rows (**10.6 %**) |
| Survival by era | 67.9 % (pre-1970) to 74.8 % (2000s) |

Open **[Midterm/](./Midterm)** for the plan PDF, presentation, notebook, and `pilot_output/`.

---

## Final project (upcoming)

The final project will build on the midterm curation plan and pilot. Expected contents (to be added):

- Final report with full supporting documentation
- Any extended pipeline, governance, or evaluation work beyond the pilot
- Updated reflections on what changed from midterm to final

Until the final is published, the **Midterm** folder is the complete, portfolio-ready artifact for this workstream.

---

## Repository layout
```
Rotten-Tomatoes-Curation-Plan/
├── README.md                 ← this file
└── Midterm/
├── README.md
├── Midterm_Project_Curation_Plan_and_Pilot_Chloe_Kaire_ITAI_3375.pdf
├── Midterm_Presentation_ITAI3375.pdf
├── Rotten_tomatoes_pilot_ITAI_3375.ipynb
├── pilot_output/         ← cleaned CSVs, rejects, JSON reports, hand-audit sample
└── data/                 ← instructions only (full source CSVs from Kaggle, not committed)
```

---

## How a stranger should navigate

1. Start with **[Midterm/README.md](./Midterm/README.md)** for the full story (problem, method, results, failures).
2. Open the notebook for the executable pilot.
3. Inspect `Midterm/pilot_output/` for the cleaned and rejected tables.
4. Return here later for the **Final** folder when it is published.

---

## Course context

Part of the ITAI 3375 course portfolio. Designed as hiring evidence of judgment: quantified quality problems, tested fixes, and explicit reporting of what did not work — including the 64.5 % letter-grade mapping failure and the circular nature of the site-aligned alternative.
