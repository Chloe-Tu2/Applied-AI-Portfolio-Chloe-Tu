# Curating Data for A.I. Optimization — ITAI 3375

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![pandas](https://img.shields.io/badge/library-pandas-150458.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![Kaggle](https://img.shields.io/badge/platform-Kaggle-20BEFF.svg)
![Excel](https://img.shields.io/badge/tool-Excel-217346.svg)
![Data Curation](https://img.shields.io/badge/topic-Data_Curation-9cf.svg)
![FAIR](https://img.shields.io/badge/principle-FAIR-blueviolet.svg)
![Quality Audit](https://img.shields.io/badge/topic-Quality_Audit-orange.svg)
![Governance](https://img.shields.io/badge/topic-Governance-4B0082.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## Course Overview

This repository documents a full semester of applied data curation work completed for **ITAI 3375 – Curating Data for A.I. Optimization** at Houston City College, part of the Applied AI & Robotics program. The course treats data not as a passive input to machine learning but as a managed asset with its own lifecycle, quality requirements, licensing constraints, and financial value. Students learn to profile, audit, license-check, document, and govern datasets so they are defensible and genuinely usable for AI systems. Every project in this portfolio reflects a real curation decision—what to keep, what to reject, what to document, and what to report honestly when things fail.

## Featured Capstone / Midterm Project

**Rotten Tomatoes Curation Plan and Pilot** — Team: Chloe Tu & Kaire Campomanes

| Fact | Detail |
|------|--------|
| Dataset | Rotten Tomatoes movies + critic reviews (Kaggle, stefanoleone992), CC0 1.0 |
| Scale | 17,712 movies · 1,130,017 critic reviews |
| Core problem | `review_score` appeared in **814 distinct string forms** and was missing in **27.1 %** of reviews |
| Pilot sample | 50,000 reviews (seeded, reproducible) |
| Survival rate | **72.4 %** of rows survived normalization to a 0–100 scale |
| Failure reported | First letter-grade mapping agreed with the site's own Fresh/Rotten label only **64.5 %** of the time—reported as a failure, not hidden |
| Deliverables | Full curation plan PDF, presentation PDF, working pilot notebook |

→ **[View the Midterm project folder](Midterm-Rotten-Tomatoes-Curation-Pilot/)**

## Project Directory

### Foundations & Industry Context
| Folder | Description |
|--------|-------------|
| [Project-01](Project-01-Curation-in-Your-Industry/) | Curation challenges at Meta: algorithmic content engineering and multimodal data |
| [Project-02](Project-02-Profile-the-Job-Market-You-Are-Entering/) | Job market analysis for cloud, AI, and data engineering roles |
| [Project-03](Project-03-The-FAIR-and-Open-Memo/) | Memo applying FAIR and Open Data principles to a real dataset scenario |

### Quality & Licensing
| Folder | Description |
|--------|-------------|
| [Project-04](Project-04-Assess-a-Public-Dataset-as-a-Business-Asset/) | Business-asset evaluation of a public dataset |
| [Project-05](Project-05-License-Detective/) | License detection and compliance assessment for training data |
| [Project-06](Project-06-Compare-Three-Repositories-for-One-Task/) | Side-by-side comparison of three data repositories for one ML task |
| [Project-07](Project-07-Build-a-Complete-Data-Sheet/) | Full data sheet following structured documentation standards |
| [Project-08](Project-08-Run-a-Full-Quality-Audit/) | Quality audit of the Spotify + YouTube dataset (20,718 rows, 28 columns) |

### Pipelines & Datasets
| Folder | Description |
|--------|-------------|
| [Project-09](Project-09-Build-a-Small-Extraction-Pipeline/) | Extraction pipeline: 25 job postings → structured CSV with failure tracking |
| [Project-10](Project-10-Audit-an-Instruction-or-Preference-Dataset/) | Audit of an instruction/preference dataset for LLM fine-tuning |
| [Project-11](Project-11-Build-and-Evaluate-a-Small-Knowledge-Base/) | Small knowledge base construction and evaluation |
| [Project-12](Project-12-Design-a-Labeling-Pipeline/) | Labeling pipeline design with Excel-based workflow specification |
| [Project-13](Project-13-Generate-and-Evaluate-a-Synthetic-Dataset/) | Synthetic dataset generation and quality evaluation |

### Governance & Business
| Folder | Description |
|--------|-------------|
| [Project-14](Project-14-Build-a-Governance-and-Compliance-Plan/) | Governance and compliance plan for AI data operations |
| [Project-15](Project-15-The-Budget-Reduction-Memo/) | Memo: how to cut a data curation budget while preserving quality |
| [Project-16](Project-16-Build-a-Cost-Model-and-Business-Case/) | Cost model and business case for a data curation initiative |

## Notebooks & Technical Artifacts Overview

| Artifact | Type | Key Detail |
|----------|------|------------|
| P08 Quality Audit | Jupyter notebook + PDF | Spotify + YouTube dataset; missingness charts; critical column analysis |
| P09 Extraction Pipeline | Jupyter notebook + CSV | 25 files → structured table; 8 of 25 rows had at least one extraction failure |
| P12 Labeling Pipeline | PDF + Excel | Pipeline design with role assignments and quality gates |
| P13 Synthetic Dataset | PDF + CSV | Generated dataset with evaluation against real-data baselines |
| P16 Cost Model | PDF + Excel | Line-item cost model with ROI projection |
| Midterm Pilot | Jupyter notebook | Rotten Tomatoes score normalization; 50,000-row sample; rejected-row tracking |

## Key Learning Outcomes

- **Data as an asset:** Learned to evaluate datasets as financial and semantic investments, not free inputs—cost, license risk, and replacement cost all matter.
- **FAIR and Open principles:** Applied Findability, Accessibility, Interoperability, and Reusability criteria to real datasets and identified where each failed.
- **License detection:** Practiced tracing license provenance through derivative and aggregated datasets where the license chain was unclear.
- **Quality auditing with quantified failure rates:** Audited 20,718 rows across 28 columns (P08) and 1.13 M reviews (midterm); reported exact missing rates, duplicate counts, and placeholder dates.
- **Data sheets and documentation:** Built complete data sheets that a stranger could use to evaluate fitness for purpose without running any code.
- **Pipeline design:** Designed extraction, labeling, and synthetic-data pipelines with explicit failure-handling and reject tracking.
- **Governance, compliance, and cost modeling:** Created governance plans, budget-reduction memos, and cost models grounded in realistic line items.
- **Honest failure reporting:** Every project reports what did not work, what was sampled, how many problems were found, and what would be done differently.

## Tools & Frameworks

Python · pandas · Jupyter / Google Colab · Kaggle / kagglehub · matplotlib · Excel · PDF documentation · GitHub

## Real-World Applications

The skills demonstrated here map directly to roles such as **Data Curator**, **ML Data Engineer**, **Content/Knowledge Engineer**, **AI Governance Specialist**, and vendor due-diligence analyst. Organizations building or buying training data need people who can assess quality before it reaches a model, detect license risk before it becomes legal exposure, and build the documentation that makes a dataset defensible under audit. These are judgment-heavy roles that cannot be automated away.

## Repository Structure

```
Curating-Data-for-AI-Optimization-ITAI3375/
├── README.md
│
├── Midterm-Rotten-Tomatoes-Curation-Pilot/
│   ├── README.md
│   ├── Midterm_Project_Curation_Plan_and_Pilot_Chloe_Kaire_ITAI_3375.pdf
│   ├── Midterm_Presentation_ITAI3375.pdf
│   └── Rotten_tomatoes_pilot_ITAI_3375.ipynb
│
├── Project-01-Curation-in-Your-Industry/
│   ├── README.md
│   └── P01-Curation-in-Your-Industry.pdf
│
├── Project-02-Profile-the-Job-Market-You-Are-Entering/
│   ├── README.md
│   └── P02-Profile-the-Job-Market-You-Are-Entering.pdf
│
├── Project-03-The-FAIR-and-Open-Memo/
│   ├── README.md
│   └── P03-The-FAIR-and-Open-Memo.pdf
│
├── Project-04-Assess-a-Public-Dataset-as-a-Business-Asset/
│   ├── README.md
│   └── P04-Assess-a-Public-Dataset-as-a-Business-Asset.pdf
│
├── Project-05-License-Detective/
│   ├── README.md
│   └── P05-License-Detective.pdf
│
├── Project-06-Compare-Three-Repositories-for-One-Task/
│   ├── README.md
│   └── P06-Compare-Three-Repositories-for-One-Task.pdf
│
├── Project-07-Build-a-Complete-Data-Sheet/
│   ├── README.md
│   └── P07-Build-a-Complete-Data-Sheet.pdf
│
├── Project-08-Run-a-Full-Quality-Audit/
│   ├── README.md
│   ├── P08-Run-a-Full-Quality-Audit.ipynb
│   └── P08-Run-a-Full-Quality-Audit.pdf
│
├── Project-09-Build-a-Small-Extraction-Pipeline/
│   ├── README.md
│   ├── P09-Build-a-Small-Extraction-Pipeline.ipynb
│   ├── P09-Build-a-Small-Extraction-Pipeline.csv
│   └── P09-Build-a-Small-Extraction-Pipeline.pdf
│
├── Project-10-Audit-an-Instruction-or-Preference-Dataset/
│   ├── README.md
│   └── P10-Audit-an-Instruction-or-Preference-Dataset.pdf
│
├── Project-11-Build-and-Evaluate-a-Small-Knowledge-Base/
│   ├── README.md
│   └── P11-Build-and-Evaluate-a-Small-Knowledge-Base.pdf
│
├── Project-12-Design-a-Labeling-Pipeline/
│   ├── README.md
│   ├── P12-Design-a-Labeling-Pipeline.pdf
│   └── P12-Design-a-Labeling-Pipeline.xlsx
│
├── Project-13-Generate-and-Evaluate-a-Synthetic-Dataset/
│   ├── README.md
│   ├── P13-Generate-and-Evaluate-a-Synthetic-Dataset.pdf
│   └── P13-Generate-and-Evaluate-a-Synthetic-Dataset.csv
│
├── Project-14-Build-a-Governance-and-Compliance-Plan/
│   ├── README.md
│   └── P14-Build-a-Governance-and-Compliance-Plan.pdf
│
├── Project-15-The-Budget-Reduction-Memo/
│   ├── README.md
│   └── P15-The-Budget-Reduction-Memo.pdf
│
└── Project-16-Build-a-Cost-Model-and-Business-Case/
    ├── README.md
    ├── P16-Build-a-Cost-Model-and-Business-Case.pdf
    └── P16-Build-a-Cost-Model-and-Business-Case.xlsx
```

## How to Navigate

If you are a recruiter or interviewer, start with the **[Midterm folder](Midterm-Rotten-Tomatoes-Curation-Pilot/)** — it is the most substantial piece and demonstrates end-to-end curation thinking with real data and honest failure reporting. Then look at **[Project-08](Project-08-Run-a-Full-Quality-Audit/)** (quality audit with quantified findings), **[Project-14](Project-14-Build-a-Governance-and-Compliance-Plan/)** (governance planning), and **[Project-07](Project-07-Build-a-Complete-Data-Sheet/)** (data sheet documentation). These four artifacts together show data judgment, technical execution, and professional documentation.
