# Project 08 — Run a Full Quality Audit

## Project Overview

This project is a hands-on quality audit of the **Spotify and YouTube** dataset (published by Salvatore Rastelli on Kaggle). The audit systematically checks completeness, uniqueness, validity, and consistency across 20,718 rows and 28 columns, producing quantified findings with visualizations.

## Problem Statement

Before any dataset is used for modeling or analysis, its quality must be measured—not assumed. This audit asks: How much is missing? Are there duplicates? Do values fall within sensible ranges? Which quality problems would actually break a downstream use case, and which are cosmetic?

## Approach and Methodology

- **Data loading:** Downloaded via `kagglehub` (Kaggle API). 20,718 rows, 28 columns.
- **Completeness:** Counted missing values per column. Worst: `Description` (876 missing, 4.2 %), `Stream` (576 missing, 2.8 %), `Comments` (569, 2.7 %), `Likes` (541, 2.6 %). Ten YouTube-side columns each missing ~470 values (2.3 %).
- **Critical column identified:** `Stream` (Spotify play count) is the most important missing column—it is the primary outcome variable, and its absence makes 576 rows unusable for any streaming-popularity analysis.
- **Uniqueness:** Zero exact duplicate rows. However, `Uri` (Spotify track URI, which should be unique) had only 18,862 distinct values across 20,718 rows—~1,856 rows share a URI, indicating the data was collected per-artist without deduplication.
- **Validity:** Checked numeric ranges. `Tempo` has a minimum of 0.0 (likely a placeholder). `Duration_ms` maximum is 4,676,058 ms (~78 minutes), plausible for extended tracks.
- **Visualization:** Horizontal bar chart of missingness rates for the worst columns.

## Results and Evaluation

| Finding | Detail |
|---------|--------|
| Total rows / columns | 20,718 / 28 |
| Most missing column | `Description` (4.2 %) |
| Critical missing column | `Stream` (2.8 %) — primary outcome variable |
| Exact duplicates | 0 |
| URI uniqueness gap | ~1,856 rows share a URI with another row |
| Suspicious values | `Tempo` = 0.0 (likely placeholder, not a real tempo) |

## Learning Outcomes & Reflection

- **Difficult:** Deciding which missing column "matters most" required understanding the dataset's intended use, not just counting nulls. `Description` had the highest missing rate but is analytically irrelevant; `Stream` has a lower rate but is the outcome variable.
- **What failed:** The uniqueness check initially focused only on exact duplicate rows (found 0) and nearly missed the URI issue. Had to revisit and check per-column uniqueness to catch it.
- **What would change:** Would add a consistency check between Spotify and YouTube metrics (e.g., do high-stream tracks always have high-view YouTube videos?) and flag rows where the cross-platform relationship is anomalous.

## Project Files

| File | Description |
|------|-------------|
| `P08-Run-a-Full-Quality-Audit.ipynb` | Jupyter notebook with full audit code and outputs |
| `P08-Run-a-Full-Quality-Audit.pdf` | PDF export of the notebook |

## Project Structure

```
Project-08-Run-a-Full-Quality-Audit/
├── README.md
├── P08-Run-a-Full-Quality-Audit.ipynb
└── P08-Run-a-Full-Quality-Audit.pdf
```

## Dependencies / Requirements

- Python 3.x, pandas, matplotlib, kagglehub
- Google Colab or Jupyter with internet access
- Kaggle credentials (for dataset download)

## Data Access

Dataset: [Spotify and YouTube](https://www.kaggle.com/datasets/salvatorerastelli/spotify-and-youtube) by Salvatore Rastelli on Kaggle. Downloaded via `kagglehub.dataset_download("salvatorerastelli/spotify-and-youtube")`.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Core technical assignment demonstrating systematic quality assessment with quantified findings and honest judgment about what matters.
