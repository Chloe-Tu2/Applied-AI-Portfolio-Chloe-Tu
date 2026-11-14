# Project 01 — Curation in Your Industry

![Industry Analysis](https://img.shields.io/badge/topic-Industry_Analysis-9cf.svg)
![Meta](https://img.shields.io/badge/org-Meta-0668E1.svg)
![Content Engineering](https://img.shields.io/badge/domain-Content_Engineering-blueviolet.svg)
![Job Market](https://img.shields.io/badge/focus-Job_Market-orange.svg)
![PDF](https://img.shields.io/badge/format-PDF-red.svg)

## Project Overview

This project examines data curation challenges in the technology industry, focusing on Meta's algorithmic content engineering operations. The analysis centers on the role of a Product Content Engineer and how multimodal data (text, images, video, engagement signals) must be curated to train and evaluate recommendation and content-ranking systems.

## Problem Statement

Large-scale content platforms like Meta ingest billions of multimodal data points daily. The curation challenge is not volume but judgment: deciding what data represents genuine user intent versus engagement artifacts, how to handle adversarial content, and how to build evaluation datasets that reflect real-world distribution without amplifying harmful patterns.

## Approach and Methodology

- Researched Meta's public documentation on content ranking and integrity systems
- Identified the Product Content Engineer role as a key curation position
- Analyzed the types of data involved: text posts, image features, video metadata, engagement time-series, and human evaluation labels
- Mapped curation decisions to downstream AI quality: what happens when training data is mislabeled, skewed, or adversarially polluted

## Results and Evaluation

The deliverable is a written analysis (PDF) identifying three critical curation decisions specific to algorithmic content engineering: (1) how to define and measure "quality" engagement versus clickbait engagement, (2) how to curate evaluation datasets that avoid popularity bias, and (3) how to handle multilingual content where labeling quality varies by language.

## Learning Outcomes & Reflection

- **Difficult:** Identifying curation decisions that are specific to one industry rather than generic was harder than expected. Early drafts read like a general data quality checklist.
- **What would change:** Would have interviewed or cited more practitioners to ground the analysis in real operational constraints rather than public-facing documentation alone.
- **Incomplete:** The multimodal angle was underdeveloped—stated that images and video matter but did not detail how curation differs for each modality.

## Project Files

| File | Description |
|------|-------------|
| `P01-Curation-in-Your-Industry.pdf` | Written analysis document |

## Project Structure

```
Project-01-Curation-in-Your-Industry/
├── README.md
└── P01-Curation-in-Your-Industry.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

No dataset was used directly. Analysis draws on publicly available information about Meta's content systems.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Early-term assignment exploring how data curation operates within a specific industry and role.
