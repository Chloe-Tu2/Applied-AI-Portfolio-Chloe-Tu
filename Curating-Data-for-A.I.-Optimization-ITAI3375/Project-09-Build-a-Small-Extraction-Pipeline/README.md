# Project 09 — Build a Small Extraction Pipeline

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![pandas](https://img.shields.io/badge/library-pandas-150458.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![ETL](https://img.shields.io/badge/topic-ETL_Pipeline-orange.svg)
![CSV](https://img.shields.io/badge/output-CSV-green.svg)
![Extraction](https://img.shields.io/badge/task-Extraction-9cf.svg)

## Project Overview

This project builds a small extraction pipeline that reads 25 unstructured job posting text files and produces a structured CSV table with five fields: job title, organization, location, pay range, and required skills. The pipeline tracks and reports every extraction failure.

## Problem Statement

Unstructured text is abundant; structured data is scarce. Converting one to the other requires explicit schema decisions (what to extract), pattern definitions (how to extract it), and failure handling (what to do when patterns do not match). This project practices all three.

## Approach and Methodology

- **Source files:** 25 plain-text job postings (`.txt`), each following a 5-line structure. Intentionally seeded with three categories of formatting inconsistency to simulate real-world variation.
- **Schema:** Five fields: `job_title`, `organization`, `location`, `pay`, `skills`.
- **Extraction rules:** Job title and organization from line positions. Location via regex `([A-Z][a-zA-Z .]+,\s*[A-Z]{2})`. Pay via regex `(\$[\d,]+(?:\s*-\s*\$[\d,]+)?)`. Skills via keyword trigger `"Requires"`.
- **Failure tracking:** Every file that fails any extraction records the failure reason. No files are silently dropped.
- **Inventory first:** Before extraction, inventoried all 25 files: confirmed all readable, all `.txt`, sizes 121–177 bytes.

## Results and Evaluation

| Metric | Count |
|--------|-------|
| Files processed | 25 of 25 |
| Files with complete extraction | 17 |
| Pay extraction failures | 3 (salary listed as "Pay range not provided by employer") |
| Location extraction failures | 2 (non-standard format: "Remote / Houston Texas") |
| Skills extraction failures | 3 (phrased as "Must have experience with" instead of "Requires") |
| Location false match | 1 (company name matched the city/state regex: "Greenberg Traurig, LL") |

8 of 25 rows (32 %) had at least one null field. The false match on the company name "Greenberg Traurig, LLP" being captured as a location was an unexpected regex failure.

## Learning Outcomes & Reflection

- **Difficult:** Writing regex patterns that are specific enough to avoid false matches but general enough to handle legitimate variation. The location regex false-matched on a company name.
- **What failed:** The skills extraction was brittle—dependent on a single keyword ("Requires"). Three postings used different phrasing and returned null. A real pipeline would need NLP-based extraction or multiple keyword patterns.
- **What would change:** Would add a second-pass extraction for failed fields using alternative patterns, and would validate location extractions against a known city list to catch false matches like "Greenberg Traurig."

## Project Files

| File | Description |
|------|-------------|
| `P09-Build-a-Small-Extraction-Pipeline.ipynb` | Jupyter notebook with pipeline code and outputs |
| `P09-Build-a-Small-Extraction-Pipeline.csv` | Extracted structured data (25 rows) |
| `P09-Build-a-Small-Extraction-Pipeline.pdf` | PDF export of the notebook |

## Project Structure

```
Project-09-Build-a-Small-Extraction-Pipeline/
├── README.md
├── P09-Build-a-Small-Extraction-Pipeline.ipynb
├── P09-Build-a-Small-Extraction-Pipeline.csv
└── P09-Build-a-Small-Extraction-Pipeline.pdf
```

## Dependencies / Requirements

- Python 3.x, pandas, re (standard library), pathlib (standard library)
- Google Colab or Jupyter

## Data Access

Source files are generated programmatically by the notebook (25 synthetic job postings). No external dataset download is required.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Pipeline-building assignment emphasizing schema decisions, pattern-based extraction, and transparent failure reporting. The vendor due-diligence question set from this project (understanding extraction failure modes) is a genuinely useful working artifact.
