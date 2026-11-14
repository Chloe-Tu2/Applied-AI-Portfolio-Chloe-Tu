# Project 03 — The FAIR and Open Memo
![FAIR](https://img.shields.io/badge/principle-FAIR-blueviolet.svg)
![Open Data](https://img.shields.io/badge/principle-Open_Data-9cf.svg)
![Policy Memo](https://img.shields.io/badge/type-Policy_Memo-orange.svg)
![PDF](https://img.shields.io/badge/format-PDF-red.svg)

## Project Overview

This project is a policy memo applying the FAIR (Findable, Accessible, Interoperable, Reusable) and Open Data principles to a real dataset scenario. The memo evaluates how well a specific dataset meets each FAIR criterion and recommends concrete steps to close the gaps.

## Problem Statement

FAIR principles are widely cited but rarely applied with specificity. Many datasets claim to be "open" without satisfying basic findability or interoperability requirements. This memo forces a concrete, criterion-by-criterion evaluation rather than a vague endorsement.

## Approach and Methodology

- Selected a specific public dataset and assessed it against each of the 15 FAIR sub-principles (F1–F4, A1–A2, I1–I3, R1–R1.3)
- Distinguished between "Open" (legal permission to use) and "FAIR" (technical usability), which are often conflated
- Identified the weakest FAIR dimensions for the chosen dataset and proposed specific remediation steps
- Wrote findings as a professional memo addressed to a decision-maker

## Results and Evaluation

The memo found that most publicly available datasets satisfy Findability (they have DOIs or stable URLs) and Accessibility (they are downloadable) but fail on Interoperability (no standardized schema or controlled vocabulary) and Reusability (license present but provenance and data dictionaries missing or incomplete).

## Learning Outcomes & Reflection

- **Difficult:** Distinguishing between the spirit of FAIR (good documentation practices) and the letter of FAIR (specific sub-principles about persistent identifiers and machine-readable metadata) was more nuanced than expected.
- **What failed:** The initial draft conflated "open license" with "FAIR," which the assignment was explicitly designed to prevent. Had to rewrite after recognizing the distinction.
- **What would change:** Would include a scoring rubric (e.g., 0–2 per sub-principle) to make the assessment more systematic and comparable across datasets.

## Project Files

| File | Description |
|------|-------------|
| `P03-The-FAIR-and-Open-Memo.pdf` | Policy memo document |

## Project Structure

```
Project-03-The-FAIR-and-Open-Memo/
├── README.md
└── P03-The-FAIR-and-Open-Memo.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

The dataset evaluated is referenced within the memo. No data files are included in this folder.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Foundational assignment on data governance principles and the distinction between openness and usability.
