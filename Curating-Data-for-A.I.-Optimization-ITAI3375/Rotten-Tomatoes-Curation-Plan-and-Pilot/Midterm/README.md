# Midterm — Rotten Tomatoes Curation Plan and Pilot

**Team:** Chloe Tu, Kaire Campomanes  
**Course:** ITAI 3375 – Curating DATA for A.I. Optimization  
**Date:** October 2026

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![pandas](https://img.shields.io/badge/library-pandas-150458.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![Kaggle](https://img.shields.io/badge/platform-Kaggle-20BEFF.svg)
![Data Quality](https://img.shields.io/badge/topic-Data_Quality-orange.svg)
![CC0](https://img.shields.io/badge/license-CC0_1.0-lightgrey.svg)

**Start here:** open `Rotten_tomatoes_pilot_ITAI_3375.ipynb` for the working pilot; the PDF is the full plan.

---

## Project Overview

This midterm delivers a full data curation plan and a working pilot for the Rotten Tomatoes movies and critic reviews dataset. The team designed a plan to make the dataset usable for AI systems that need structured, numeric review scores—then tested the riskiest assumption (score normalization) on a 50,000-row sample.

## Problem Statement

The Rotten Tomatoes critic reviews dataset contains **1,130,017 reviews** across **17,712 movies**, but the `review_score` field is nearly unusable in its raw form. Scores appear in **814 distinct string formats**:

| Format | Share of scored reviews |
|--------|-------------------------|
| Fractions (31 different denominators) | 61.4 % |
| Letter grades A+ through F | 11.4 % |
| Bare numbers with no scale | 0.14 % |
| Missing entirely | **27.1 %** of all reviews |

Any downstream model or analysis needs these scores on a single numeric scale. Naïve conversion risks distorting or silently dropping large portions of the data.

## Approach and Methodology

- **Data source:** Kaggle (stefanoleone992), CC0 1.0 license. Downloaded via `kagglehub` with SHA-256 verification.
- **Profiling:** Counted missingness per column across both tables. Identified 48.4 % missing `critics_consensus` in movies and 27.1 % missing `review_score` in reviews.
- **Duplicate detection:** Found 119,471 exact duplicate review rows (**10.6 %** of all reviews). Dates as early as 1800-01-01 flagged as placeholders; 48,019 reviews dated exactly 2000-01-01 (4.25 %).
- **Score normalization:** Fractions → percentage of denominator. Letter grades → numeric via two competing mapping tables (school-style vs site-aligned). Bare numbers and malformed fractions rejected with reasons logged.
- **Pilot sample:** 50,000 reviews, seeded (`random_state=42`) for reproducibility.
- **Equity checks:** Missingness and survival rates broken out by decade, genre, top-critic flag, and publisher size.
- **Manual audit:** 100 records read by hand. **47 had at least one problem** (37 found by rule, 10 only by reading). Issues included excerpt-only text, inconsistent publisher names, multi-critic fields, and label/score contradictions.

## Results and Evaluation

| Metric | Value |
|--------|-------|
| Rows surviving normalization | 36,203 of 50,000 (**72.4 %**) |
| Overall label agreement (school mapping) | 89.7 % |
| Fraction-only label agreement | 94.4 % |
| Letter-grade label agreement (school mapping) | **64.5 %** — a failure |
| Letter-grade label agreement (site-aligned mapping) | 100 % (circular — see note) |
| Survival rate range by era | 67.9 % (pre-1970) to 74.8 % (2000s) |

**Important note on the 64.5 % failure:** The site treats every C and below as Rotten, so a standard school-grade mapping assigns Fresh to grades that the site calls Rotten. A site-aligned mapping achieves 100 % agreement, but that agreement is circular because the mapping was derived from the labels. This was reported as a failure, not hidden.

## Learning Outcomes & Reflection

- **What was difficult:** The sheer variety of score formats was harder than expected. We assumed 5–10 formats; there were 814.
- **What failed:** The first letter-grade mapping produced only 64.5 % agreement with the site's own labels. We spent time debugging before realizing the site's Fresh/Rotten threshold for letter grades is not the school-grade threshold.
- **What was incomplete:** Duplicates were not removed before sampling, which hid a 10.6 % duplication rate (only 0.43 % was visible in the sample). This is a methodological error we documented but did not fix in the pilot scope.
- **What we would change:** Remove duplicates before sampling. Use stratified sampling by score format to ensure adequate coverage of rare formats. Investigate the 48,019 placeholder dates before deciding whether to keep those rows. Build a small validation set with manually verified scores to measure mapping accuracy without circularity.
- **Sampling:** 100 records read by hand; 47 had problems. 50,000-row pilot sample; 72.4 % survived.

## Project Files

| File | Description |
|------|-------------|
| `Midterm_Project_Curation_Plan_and_Pilot_Chloe_Kaire_ITAI_3375.pdf` | Full curation plan document |
| `Midterm_Presentation_ITAI3375.pdf` | Presentation slides |
| `Rotten_tomatoes_pilot_ITAI_3375.ipynb` | Working pilot notebook (Python, pandas, kagglehub) |
| `pilot_output/` | Cleaned tables, reject tables, JSON reports, manual audit sample |
| `data/` | Instructions for obtaining source CSVs (~243 MB; not committed) |

## Project Structure
```
Midterm/
├── README.md
├── Midterm_Project_Curation_Plan_and_Pilot_Chloe_Kaire_ITAI_3375.pdf
├── Midterm_Presentation_ITAI3375.pdf
├── Rotten_tomatoes_pilot_ITAI_3375.ipynb
├── pilot_output/
│   ├── pilot_cleaned_school.csv
│   ├── pilot_cleaned_site_aligned.csv
│   ├── pilot_rejects_school.csv
│   ├── pilot_rejects_site_aligned.csv
│   ├── pilot_report_school.json
│   ├── pilot_report_site_aligned.json
│   ├── manual_audit_sample.csv
│   └── README.md
└── data/
└── README.md
```

## Dependencies / Requirements

- Python 3.x, pandas, numpy, kagglehub, matplotlib
- Google Colab or Jupyter with internet access (for Kaggle download)
- Kaggle credentials (for `kagglehub.dataset_download`)

## Data Access

Dataset: [Rotten Tomatoes Movies and Critic Reviews](https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset) by stefanoleone992 on Kaggle. License: CC0 1.0 (public domain). The notebook downloads data automatically via `kagglehub`; a local fallback path is provided. Full source CSVs (~243 MB) are not stored in this repository — see `data/README.md`. All pilot outputs are under `pilot_output/`.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College, Applied AI & Robotics program. This was the midterm project (team of two: Chloe Tu and Kaire Campomanes). The assignment required a full curation plan for a real dataset and a working pilot that tested the plan's riskiest assumption.
