# Project 16 — Build a Cost Model and Business Case

## Project Overview

This project builds a cost model for a data curation initiative and wraps it in a business case that justifies the investment. The cost model is an Excel workbook with line-item costs; the business case is a written document that connects those costs to measurable business outcomes.

## Problem Statement

Data curation is expensive, and its value is often invisible until something goes wrong (a model fails, a compliance violation is discovered, a biased dataset causes reputational damage). A cost model and business case make the investment visible and defensible to decision-makers who control budgets.

## Approach and Methodology

- Identified all cost categories: labor (by role and seniority), tooling/infrastructure, data acquisition, quality assurance, governance/compliance, and overhead
- Estimated costs per unit (e.g., cost per labeled record, cost per audit cycle, cost per GB stored)
- Built an Excel model that calculates total cost under different scenarios (baseline, expanded, reduced)
- Wrote a business case document that connects costs to value: risk reduction, model accuracy improvement, regulatory compliance, and time-to-production for new AI initiatives

## Results and Evaluation

The Excel workbook provides a transparent, adjustable cost model. The business case document argues that the curation investment pays for itself primarily through risk reduction (avoiding costly compliance failures) and efficiency gains (reducing the time data scientists spend cleaning data).

## Learning Outcomes & Reflection

- **Difficult:** Quantifying the value side of the business case. Cost is concrete; value is often indirect (avoiding a fine, preventing a model failure). Making the value claims credible without overstating them was the main challenge.
- **What failed:** The initial model did not account for the ongoing cost of maintaining curated data over time—only the initial curation cost. Added a maintenance and refresh cost line in revision.
- **What would change:** Would validate the unit costs against published industry benchmarks or vendor quotes rather than relying solely on internal estimates. Would also add sensitivity analysis showing how the business case changes if key assumptions (error rates, fine risk, model accuracy impact) vary.

## Project Files

| File | Description |
|------|-------------|
| `P16-Build-a-Cost-Model-and-Business-Case.pdf` | Business case document |
| `P16-Build-a-Cost-Model-and-Business-Case.xlsx` | Excel cost model workbook |

## Project Structure

```
Project-16-Build-a-Cost-Model-and-Business-Case/
├── README.md
├── P16-Build-a-Cost-Model-and-Business-Case.pdf
└── P16-Build-a-Cost-Model-and-Business-Case.xlsx
```

## Dependencies / Requirements

PDF viewer and Microsoft Excel (or compatible spreadsheet application).

## Data Access

No external dataset required. The Excel file contains the cost model.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Final assignment synthesizing technical and business skills—building the financial argument for work that is often undervalued because its benefits are preventive rather than visible.
