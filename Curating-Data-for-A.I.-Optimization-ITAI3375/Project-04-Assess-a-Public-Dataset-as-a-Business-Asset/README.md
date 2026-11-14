# Project 04 — Assess a Public Dataset as a Business Asset

## Project Overview

This project evaluates a public dataset as if it were a business asset being considered for acquisition. The assessment covers data quality, license terms, maintenance trajectory, replacement cost, and fitness for a specific AI use case.

## Problem Statement

Organizations often treat public datasets as "free." In practice, a dataset that is free to download may carry hidden costs: cleaning effort, license risk, lack of maintenance, and fitness gaps that require supplementation. This project applies a business-asset lens to make those costs visible.

## Approach and Methodology

- Selected a public dataset relevant to an AI application
- Evaluated along five dimensions: (1) quality and completeness, (2) license and legal risk, (3) maintenance and update frequency, (4) replacement cost if the dataset disappeared, (5) fitness for the intended AI task
- Estimated the labor cost of cleaning and supplementing the dataset to production readiness
- Compared against alternatives (commercial datasets, internal collection, synthetic generation)

## Results and Evaluation

The assessment found that even CC0-licensed datasets carry significant implicit costs. The chosen dataset required estimated cleaning effort of 20–40 hours for a single engineer, and its update cadence (infrequent or abandoned) created risk for any application requiring current data. Replacement cost was estimated based on manual collection rates.

## Learning Outcomes & Reflection

- **Difficult:** Estimating replacement cost required assumptions about collection speed and labor rates that felt speculative. The numbers are defensible but imprecise.
- **What failed:** Initial assessment focused too heavily on data quality and underweighted license and maintenance risk. Revised after feedback.
- **What would change:** Would build a reusable scoring template rather than a one-off narrative, making future dataset assessments faster and more consistent.

## Project Files

| File | Description |
|------|-------------|
| `P04-Assess-a-Public-Dataset-as-a-Business-Asset.pdf` | Business asset evaluation document |

## Project Structure

```
Project-04-Assess-a-Public-Dataset-as-a-Business-Asset/
├── README.md
└── P04-Assess-a-Public-Dataset-as-a-Business-Asset.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

The dataset evaluated is referenced within the document. No data files are included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Mid-term assignment shifting perspective from technical quality to business value and risk.
