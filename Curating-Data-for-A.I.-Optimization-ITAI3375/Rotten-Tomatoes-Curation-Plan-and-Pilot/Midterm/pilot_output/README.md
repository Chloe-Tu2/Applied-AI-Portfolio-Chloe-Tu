# Pilot output

Artifacts produced by `Rotten_tomatoes_pilot_ITAI_3375.ipynb` on a seeded 50,000-row sample of Rotten Tomatoes critic reviews.

![CSV](https://img.shields.io/badge/format-CSV-green.svg)
![JSON](https://img.shields.io/badge/format-JSON-yellow.svg)
![Data Quality](https://img.shields.io/badge/topic-Data_Quality-orange.svg)

---

## What is in this folder

| File | Description |
|------|-------------|
| `pilot_cleaned_school.csv` | Rows that survived **school-style** score normalization (0–100) |
| `pilot_cleaned_site_aligned.csv` | Rows that survived **site-aligned** score normalization (0–100) |
| `pilot_rejects_school.csv` | Rows rejected under school-style rules, with rejection reason |
| `pilot_rejects_site_aligned.csv` | Rows rejected under site-aligned rules, with rejection reason |
| `pilot_report_school.json` | Summary metrics for the school-style run |
| `pilot_report_site_aligned.json` | Summary metrics for the site-aligned run |
| `manual_audit_sample.csv` | 100-row hand-audit sample used in the qualitative review |

---

## Key results (from the pilot)

| Metric | Value |
|--------|-------|
| Sample size | 50,000 reviews (seeded, `random_state=42`) |
| Survival rate | **72.4 %** (36,203 rows kept) |
| Letter-grade agreement (school mapping) | **64.5 %** with site Fresh/Rotten — treated as a failure |
| Hand audit | 100 records; **47** had at least one problem |

Two competing letter-grade mappings were tested. The school-style mapping was rejected because it disagreed with the platform’s own Fresh/Rotten labels too often. The site-aligned mapping was retained for downstream use.

---

## How these files were produced

1. Load movies + reviews from Kaggle (or local `data/`).
2. Sample 50,000 review rows with a fixed seed.
3. Classify `review_score` into format families (fraction, letter grade, bare number, missing, other).
4. Normalize fractions and letter grades to a 0–100 scale under two rule sets.
5. Write kept rows → `pilot_cleaned_*.csv`.
6. Write dropped rows + reason → `pilot_rejects_*.csv`.
7. Write aggregate counts → `pilot_report_*.json`.
8. Export the 100-row manual audit set → `manual_audit_sample.csv`.

Re-run the notebook to regenerate any of these files.

---

## Note on source data

The full source tables (~243 MB) are **not** stored here. They are downloaded at runtime by the notebook or obtained from Kaggle (CC0 1.0). See `../data/README.md`.
