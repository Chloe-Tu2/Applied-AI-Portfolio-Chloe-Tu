# Project 12 — Design a Labeling Pipeline

## Project Overview

This project designs a complete labeling pipeline: the process by which raw data is annotated with the labels a supervised learning model needs. The design covers role definitions, task instructions, quality gates, disagreement resolution, and throughput estimation.

## Problem Statement

Labeling is the most labor-intensive and error-prone step in most ML data pipelines. Without a designed process—clear instructions, trained annotators, inter-rater checks, and escalation paths—label quality degrades silently and the resulting model inherits systematic biases.

## Approach and Methodology

- Defined the labeling task: what is being labeled, what the label categories are, and what constitutes a correct label
- Designed the pipeline stages: onboarding, practice rounds, production labeling, quality sampling, and disagreement resolution
- Specified roles: annotators, reviewers, and a tie-breaking adjudicator
- Created the task instructions and examples in a format suitable for distribution (Excel workbook)
- Estimated throughput and cost based on assumed annotation speeds

## Results and Evaluation

The deliverable includes a written pipeline design (PDF) and an Excel workbook with task instructions, label definitions, example annotations, and a quality-tracking sheet. The design includes a quality gate: if sampled inter-annotator agreement falls below a defined threshold, production labeling pauses for recalibration.

## Learning Outcomes & Reflection

- **Difficult:** Writing labeling instructions that are unambiguous is surprisingly hard. The first version of the instructions produced different interpretations among test readers.
- **What failed:** The throughput estimate was based on assumptions about annotation speed that were not validated by actual timing. The numbers are reasonable but untested.
- **What would change:** Would conduct a small pilot with 2–3 actual annotators before finalizing the instructions and throughput estimates, to identify ambiguities and calibrate speed assumptions.

## Project Files

| File | Description |
|------|-------------|
| `P12-Design-a-Labeling-Pipeline.pdf` | Pipeline design document |
| `P12-Design-a-Labeling-Pipeline.xlsx` | Excel workbook with task instructions and quality tracking |

## Project Structure

```
Project-12-Design-a-Labeling-Pipeline/
├── README.md
├── P12-Design-a-Labeling-Pipeline.pdf
└── P12-Design-a-Labeling-Pipeline.xlsx
```

## Dependencies / Requirements

PDF viewer and Microsoft Excel (or compatible spreadsheet application).

## Data Access

No external dataset required. The Excel file contains the labeling framework and examples.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment on human-in-the-loop data pipeline design—directly relevant to ML Data Engineer and Data Curator roles.
