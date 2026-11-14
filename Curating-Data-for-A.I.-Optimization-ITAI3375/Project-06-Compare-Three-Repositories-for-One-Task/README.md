# Project 06 — Compare Three Repositories for One Task

![Repository Comparison](https://img.shields.io/badge/topic-Repository_Comparison-9cf.svg)
![Source Selection](https://img.shields.io/badge/focus-Source_Selection-orange.svg)
![Decision Framework](https://img.shields.io/badge/method-Decision_Framework-blueviolet.svg)
![PDF](https://img.shields.io/badge/format-PDF-red.svg)

## Project Overview

This project compares three different data repositories (e.g., Kaggle, Hugging Face, UCI ML Repository, government data portals) as sources for a single machine learning task. The comparison evaluates each repository on data quality, documentation, licensing, ease of access, and fitness for the intended purpose.

## Problem Statement

When starting an ML project, practitioners often default to the first dataset they find on the first platform they check. This project forces a structured comparison across repositories to reveal how much the choice of source affects the quality and usability of the data you get.

## Approach and Methodology

- Defined a specific ML task (e.g., classification, recommendation, NLP)
- Identified one relevant dataset from each of three different repositories
- Compared all three on: schema quality, completeness, documentation depth, license clarity, download/API ease, update frequency, and community support
- Summarized with a recommendation and rationale

## Results and Evaluation

The comparison revealed significant differences in documentation quality and license clarity across repositories. One repository had excellent metadata but a restrictive license; another was permissively licensed but poorly documented; the third struck a balance but had the smallest dataset. The deliverable includes a comparison table and a reasoned recommendation.

## Learning Outcomes & Reflection

- **Difficult:** Making the comparison fair when the three datasets varied in size, schema, and scope. Normalizing the comparison criteria was an iterative process.
- **What failed:** Initial comparison was too surface-level (just listing features). Revised to focus on decision-relevant differences: what would actually change if you chose repository A over B.
- **What would change:** Would add a quantitative dimension—e.g., sample 100 rows from each and count specific quality issues—rather than relying solely on metadata-level comparison.

## Project Files

| File | Description |
|------|-------------|
| `P06-Compare-Three-Repositories-for-One-Task.pdf` | Repository comparison document |

## Project Structure

```
Project-06-Compare-Three-Repositories-for-One-Task/
├── README.md
└── P06-Compare-Three-Repositories-for-One-Task.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

Datasets from the three repositories are referenced within the document. No data files are included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment on repository evaluation—a practical skill for any data acquisition workflow.
