# Project 10 — Audit an Instruction or Preference Dataset

## Project Overview

This project audits an instruction-tuning or preference dataset of the type used to fine-tune large language models (LLMs). The audit evaluates whether the data is fit for its intended purpose: teaching a model to follow instructions or align with human preferences.

## Problem Statement

Instruction and preference datasets drive the behavior of fine-tuned LLMs, yet many are assembled quickly with minimal quality control. Errors in these datasets—ambiguous instructions, contradictory preferences, mislabeled pairs—propagate directly into model behavior. Auditing before training is cheaper than debugging after deployment.

## Approach and Methodology

- Selected an instruction or preference dataset (publicly available)
- Sampled a subset of records for manual review
- Evaluated each sampled record for: instruction clarity, response correctness, preference consistency (where applicable), formatting issues, and potential safety/bias concerns
- Quantified the findings: how many records had problems, what types of problems appeared, and how severe they were

## Results and Evaluation

The audit identified issues in a meaningful fraction of sampled records. Common problems included ambiguous instructions where multiple valid responses exist, preference labels that appeared inconsistent with the content, and formatting artifacts (e.g., markdown rendering issues) that a model would learn to reproduce.

## Learning Outcomes & Reflection

- **Difficult:** Judging "correctness" of an instruction response is inherently subjective. What one reviewer calls a good answer, another might call mediocre. Establishing clear evaluation criteria before reviewing was essential.
- **What failed:** The sample size was small enough that the findings should be treated as indicative, not definitive. A statistically rigorous audit would require a larger, stratified sample.
- **What would change:** Would design a structured annotation rubric before starting the review, and would recruit a second reviewer for inter-annotator agreement measurement.

## Project Files

| File | Description |
|------|-------------|
| `P10-Audit-an-Instruction-or-Preference-Dataset.pdf` | Audit report document |

## Project Structure

```
Project-10-Audit-an-Instruction-or-Preference-Dataset/
├── README.md
└── P10-Audit-an-Instruction-or-Preference-Dataset.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

The dataset audited is referenced within the document. No data files are included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment connecting data curation to the specific needs of LLM fine-tuning, where data quality directly shapes model behavior.
