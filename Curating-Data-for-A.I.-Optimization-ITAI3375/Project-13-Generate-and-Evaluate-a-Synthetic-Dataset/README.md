# Project 13 — Generate and Evaluate a Synthetic Dataset

![Synthetic Data](https://img.shields.io/badge/topic-Synthetic_Data-9cf.svg)
![Data Generation](https://img.shields.io/badge/task-Data_Generation-orange.svg)
![CSV](https://img.shields.io/badge/output-CSV-green.svg)
![Evaluation](https://img.shields.io/badge/method-Evaluation-blueviolet.svg)
![PDF](https://img.shields.io/badge/format-PDF-red.svg)

## Project Overview

This project generates a synthetic dataset and evaluates its quality by comparing it against properties of real-world data. Synthetic data is increasingly used for training, testing, and augmentation when real data is scarce, sensitive, or expensive. This project practices the generation and tests whether the result is actually usable.

## Problem Statement

Synthetic data is only useful if it preserves the statistical properties and edge cases of real data while not simply memorizing and replaying real records. Generating synthetic data is easy; evaluating whether it is good enough for a specific purpose is the hard part.

## Approach and Methodology

- Defined the target schema and the properties the synthetic data should preserve (distributions, correlations, category frequencies)
- Generated synthetic records using rule-based or programmatic methods
- Evaluated by comparing summary statistics, distributions, and correlations between real and synthetic data
- Checked for obvious artifacts: impossible values, missing edge cases, uniform distributions where skewed ones were expected

## Results and Evaluation

The generated CSV file contains the synthetic dataset. Evaluation showed that the synthetic data preserved overall distributions reasonably well but smoothed out some tail behavior—rare categories and extreme values were underrepresented compared to the real data. This is a known limitation of the generation approach used.

## Learning Outcomes & Reflection

- **Difficult:** Deciding what "good enough" means for synthetic data. There is no universal threshold—it depends entirely on the downstream use case.
- **What failed:** The synthetic dataset underrepresented rare categories, which would be a problem for any use case specifically interested in minority classes or tail behavior.
- **What would change:** Would add targeted oversampling of rare categories during generation, and would define pass/fail criteria before generating (e.g., "category frequencies must be within 5 % of real data") to make the evaluation objective.

## Project Files

| File | Description |
|------|-------------|
| `P13-Generate-and-Evaluate-a-Synthetic-Dataset.pdf` | Generation and evaluation report |
| `P13-Generate-and-Evaluate-a-Synthetic-Dataset.csv` | Generated synthetic dataset |

## Project Structure

```
Project-13-Generate-and-Evaluate-a-Synthetic-Dataset/
├── README.md
├── P13-Generate-and-Evaluate-a-Synthetic-Dataset.pdf
└── P13-Generate-and-Evaluate-a-Synthetic-Dataset.csv
```

## Dependencies / Requirements

PDF viewer and any CSV viewer (Excel, pandas, etc.) for inspecting the synthetic data.

## Data Access

The synthetic dataset is included as a CSV file. The real-data baseline it was compared against is referenced in the report.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment on synthetic data generation—a growing area in AI data pipelines, especially where privacy or data scarcity constraints apply.
