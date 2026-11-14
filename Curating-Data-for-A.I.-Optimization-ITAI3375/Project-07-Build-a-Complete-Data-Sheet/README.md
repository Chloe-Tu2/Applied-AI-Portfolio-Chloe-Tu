# Project 07 — Build a Complete Data Sheet

## Project Overview

This project produces a complete data sheet for a dataset, following structured documentation standards. A data sheet is a permanent record of what a dataset contains, how it was collected, who created it, what it should and should not be used for, and what its known limitations are.

## Problem Statement

Most datasets ship with a one-paragraph description and a column list. This is insufficient for anyone deciding whether to use the data in a production AI system. A data sheet answers the questions that a paragraph cannot: What populations are underrepresented? What was the labeling process? What are the known failure modes?

## Approach and Methodology

- Selected a dataset and worked through the standard data sheet template sections: Motivation, Composition, Collection Process, Preprocessing/Cleaning, Uses, Distribution, and Maintenance
- For each section, answered the specific sub-questions prescribed by the template
- Where information was unavailable (e.g., the original collectors did not document their labeling process), stated that explicitly rather than guessing

## Results and Evaluation

The completed data sheet is a multi-page document that a stranger could use to decide whether the dataset fits their use case without needing to load or inspect the data. It identifies specific gaps in the original documentation—sections where the answer is "not documented by the creator"—which is itself useful information for a downstream user.

## Learning Outcomes & Reflection

- **Difficult:** The Composition section required counting things (class distributions, demographic breakdowns) that the original dataset did not make easy to compute. Some answers required writing small queries.
- **What failed:** The Maintenance section was weak because most public datasets have no maintenance plan—stating "no maintenance plan exists" is honest but feels like a gap in the deliverable.
- **What would change:** Would pair the data sheet with a notebook that programmatically computes the statistics cited in the Composition section, so the sheet can be updated when the data changes.

## Project Files

| File | Description |
|------|-------------|
| `P07-Build-a-Complete-Data-Sheet.pdf` | Complete data sheet document |

## Project Structure

```
Project-07-Build-a-Complete-Data-Sheet/
├── README.md
└── P07-Build-a-Complete-Data-Sheet.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

The dataset documented is referenced within the data sheet. No data files are included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment on structured dataset documentation—one of the most directly portfolio-relevant artifacts in the course.
