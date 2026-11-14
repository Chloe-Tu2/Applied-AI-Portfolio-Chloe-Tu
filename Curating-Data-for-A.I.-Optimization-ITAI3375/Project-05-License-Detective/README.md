# Project 05 — License Detective

## Project Overview

This project investigates the licensing status of a dataset or data artifact by tracing the full chain of provenance—from original sources through any transformations, aggregations, or redistributions—to determine what a downstream user is actually permitted to do.

## Problem Statement

Many datasets on platforms like Kaggle, Hugging Face, and GitHub carry a stated license, but that license may not cover all components of the data. A dataset assembled from multiple sources may inherit restrictive terms from any single source. Without tracing the full chain, a user risks violating terms they never read.

## Approach and Methodology

- Selected a dataset with a stated license and traced its provenance backward: Where did the data originate? Was it scraped, donated, purchased, or generated?
- Identified all intermediate transformations and redistributions
- Checked whether the stated license is legally valid given the source licenses
- Documented gaps: cases where the license chain is broken, ambiguous, or contradictory

## Results and Evaluation

The investigation found at least one case where a dataset's stated license (e.g., CC0 or MIT) could not logically apply to all of its contents because some source data was scraped from a site with explicit terms of service prohibiting redistribution. This does not mean the dataset is illegal to use, but it means the stated license is incomplete as a legal shield.

## Learning Outcomes & Reflection

- **Difficult:** License tracing is tedious and often inconclusive. Many datasets have no documented provenance, so the chain simply ends in "unknown."
- **What failed:** Could not definitively resolve whether the identified license conflict would hold up legally—that requires legal expertise, not data curation skills.
- **What would change:** Would create a structured provenance template (source → transformation → redistribution → stated license) to make the tracing process repeatable and auditable.

## Project Files

| File | Description |
|------|-------------|
| `P05-License-Detective.pdf` | License investigation document |

## Project Structure

```
Project-05-License-Detective/
├── README.md
└── P05-License-Detective.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

The datasets investigated are referenced within the document. No data files are included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment on license literacy and provenance tracing—skills essential for vendor due diligence and compliance work.
