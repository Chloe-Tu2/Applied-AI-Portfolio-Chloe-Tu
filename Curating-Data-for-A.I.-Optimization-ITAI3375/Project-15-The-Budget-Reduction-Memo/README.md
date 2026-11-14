# Project 15 — The Budget Reduction Memo

## Project Overview

This project is a decision memo responding to a budget cut scenario: a data curation operation must reduce its budget by a significant percentage while maintaining acceptable data quality. The memo recommends what to cut, what to preserve, and what the consequences of each trade-off will be.

## Problem Statement

Budget cuts are inevitable. The question is never "should we cut?" but "where do we cut with the least damage to data quality and the AI systems that depend on it?" This memo forces explicit trade-off analysis rather than across-the-board percentage reductions.

## Approach and Methodology

- Defined the current budget breakdown: labor (annotators, reviewers, engineers), tooling, data acquisition, storage, and overhead
- Identified each line item's contribution to data quality: what breaks if this item is cut?
- Proposed tiered reduction options (e.g., 10 %, 20 %, 30 %) with specific cuts for each tier
- Assessed the quality impact of each option using concrete examples (e.g., "cutting reviewer headcount by 50 % increases estimated label error rate from 3 % to 8 %")
- Recommended a preferred option with justification

## Results and Evaluation

The memo recommends a specific reduction tier and explains why the quality trade-offs at that level are acceptable while deeper cuts are not. The analysis shows that some costs (tooling, storage) can be reduced with minimal quality impact, while others (human reviewers, quality sampling) are load-bearing and cannot be cut without measurable degradation.

## Learning Outcomes & Reflection

- **Difficult:** Estimating the quality impact of budget changes without historical data on error rates at different staffing levels. The numbers are informed estimates, not empirical measurements.
- **What failed:** The first draft presented cuts without quantifying their consequences, which made the memo feel like opinion rather than analysis. Revised to include specific quality-impact estimates for each option.
- **What would change:** Would build a simple cost-quality model (even a spreadsheet) that lets a decision-maker adjust budget levers and see estimated quality outcomes dynamically.

## Project Files

| File | Description |
|------|-------------|
| `P15-The-Budget-Reduction-Memo.pdf` | Budget reduction decision memo |

## Project Structure

```
Project-15-The-Budget-Reduction-Memo/
├── README.md
└── P15-The-Budget-Reduction-Memo.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

No dataset is used. The memo addresses a hypothetical budget scenario.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Late-term assignment on the business side of data curation—demonstrating that data quality decisions are fundamentally resource-allocation decisions.
