# Project 02 — Profile the Job Market You Are Entering

## Project Overview

This project profiles the current job market for cloud computing, AI/ML engineering, and data infrastructure roles in the Houston, TX area and nationally. The goal is to understand what employers actually ask for—skills, tools, experience levels, and salary ranges—so that career planning can be grounded in evidence rather than assumptions.

## Problem Statement

Job market claims on social media and in bootcamp marketing often overstate demand for specific tools and understate the breadth of skills employers require. Without a structured survey of actual postings, it is easy to invest time in the wrong skills or misunderstand what "entry-level" means in this field.

## Approach and Methodology

- Collected and reviewed 25 job postings from major employers (Deloitte, JPMorgan Chase, Google, Chevron, Cognizant, Infosys, and others) in the Houston area
- Categorized each posting by title, employer, required skills, salary range, and seniority level
- Identified common skill clusters: Python + AWS + CI/CD, Azure + security, MLOps + Docker/Kubernetes, SQL + data governance

## Results and Evaluation

The analysis found that cloud infrastructure and AI/ML roles in Houston typically require 3–7 years of experience even for "mid-level" titles. Python and cloud platform experience (AWS or Azure) appeared in the majority of postings. Salary ranges for the 25 postings clustered between \$85,000 and \$175,000. Three postings (12 %) did not list a salary at all.

## Learning Outcomes & Reflection

- **Difficult:** Deciding what counts as a "distinct" skill versus a synonym (e.g., "cloud migration" vs. "infrastructure modernization") required judgment calls that were not always consistent.
- **What failed:** The sample of 25 postings is too small for statistically meaningful claims about the market. This is acknowledged as a limitation.
- **What would change:** Would scrape a larger sample programmatically (which was later done in Project 09) and normalize job titles before counting.

## Project Files

| File | Description |
|------|-------------|
| `P02-Profile-the-Job-Market-You-Are-Entering.pdf` | Job market analysis document |

## Project Structure

```
Project-02-Profile-the-Job-Market-You-Are-Entering/
├── README.md
└── P02-Profile-the-Job-Market-You-Are-Entering.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

Job postings were collected from public job boards. No persistent dataset is included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Early-term assignment connecting data curation skills to labor market demand.
