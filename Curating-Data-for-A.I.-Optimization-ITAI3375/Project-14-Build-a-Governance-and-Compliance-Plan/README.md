# Project 14 — Build a Governance and Compliance Plan

![Governance](https://img.shields.io/badge/topic-Governance-4B0082.svg)
![Compliance](https://img.shields.io/badge/focus-Compliance-orange.svg)
![Data Policy](https://img.shields.io/badge/artifact-Data_Policy-9cf.svg)
![Risk Management](https://img.shields.io/badge/topic-Risk_Management-red.svg)
![PDF](https://img.shields.io/badge/format-PDF-red.svg)

## Project Overview

This project creates a governance and compliance plan for an AI data operation. The plan covers data classification, access controls, retention policies, compliance with relevant regulations, audit procedures, and incident response for data quality failures.

## Problem Statement

AI systems trained on poorly governed data inherit legal, ethical, and operational risks. A governance plan is not a theoretical exercise—it is the document an organization uses to answer: Who can access this data? How long do we keep it? What happens when we discover a quality problem? What regulations apply, and how do we demonstrate compliance?

## Approach and Methodology

- Defined the scope: what data assets are covered, what AI systems consume them, and what regulations apply (e.g., GDPR, CCPA, sector-specific rules)
- Designed data classification tiers (public, internal, confidential, restricted) with corresponding access controls
- Specified retention and deletion policies aligned with regulatory requirements
- Created audit procedures: periodic quality sampling, access log review, and compliance spot checks
- Defined an incident response process for data quality failures (e.g., discovering that training data contains PII that should have been redacted)

## Results and Evaluation

The governance plan is a comprehensive PDF document organized by policy area. It is written to be actionable by a data team—not as an abstract statement of principles, but as a set of concrete procedures with defined roles, frequencies, and escalation paths.

## Learning Outcomes & Reflection

- **Difficult:** Balancing specificity (detailed enough to be actionable) with generality (applicable across multiple data assets) was a constant tension. Overly specific plans become outdated quickly; overly general ones are ignored.
- **What failed:** The initial plan did not adequately address the scenario where a third-party data vendor's compliance status changes after data has already been ingested. Added a vendor re-assessment procedure in revision.
- **What would change:** Would include a section on automated compliance monitoring (e.g., automated PII scanning, access anomaly detection) rather than relying entirely on manual audit procedures.

## Project Files

| File | Description |
|------|-------------|
| `P14-Build-a-Governance-and-Compliance-Plan.pdf` | Governance and compliance plan document |

## Project Structure

```
Project-14-Build-a-Governance-and-Compliance-Plan/
├── README.md
└── P14-Build-a-Governance-and-Compliance-Plan.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

No dataset is used directly. The plan is applied to a hypothetical or reference data operation described within the document.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Late-term assignment on governance—one of the highest-signal artifacts for demonstrating professional maturity in data operations.
