# Phase 02 — Data Pipeline and Exploratory Analysis

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Team EverGlow:** Chloe Tu, Eva Abou Abou Harb, Francisco Medina
> **Submitted:** October 2, 2026 (Weeks 4–6)

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas)](https://pandas.pydata.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter)](https://jupyter.org)
[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?logo=kaggle)](https://www.kaggle.com)

---

## Project Overview

Phase 02 built the data foundation for EverFlavor AI — the pipeline that takes raw data from six public sources and transforms it into clean, feature-engineered datasets ready for model training in Phase 03. This phase also documented all data sources, cleaning decisions, the feature schema, and the ethics/privacy framework that governs what data the system collects and how it handles user information.

**Capstone repository:** [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)
**Live app (Phase 04 result):** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)

---

## Problem Statement

Raw recipe and nutrition data from public APIs and Kaggle datasets is not ready for machine learning. Sources use different schemas, calorie estimates are often missing or wrong, cuisine labels are coarse or inconsistent (e.g., "Indian" vs "Asian" vs "South Asian"), ingredient strings are free text with no normalization, and duplicates appear across sources. Without a disciplined cleaning and feature-engineering pipeline, any model trained on this data will learn noise.

The specific challenge: build a pipeline that produces a unified dataset with reliable cuisine family labels (5 families), dietary restriction flags (pork, gluten, dairy, vegetarian, vegan), and nutrition-per-serving estimates — across multiple heterogeneous sources — while keeping documentation thorough enough that a stranger can audit every decision.

---

## Approach and Methodology

### Data Sources

| Source | Type | Use |
|--------|------|-----|
| [USDA FoodData Central](https://fdc.nal.usda.gov/) | API | Ground-truth nutrition per ingredient |
| [Open Food Facts](https://world.openfoodfacts.org/) | Open DB (CC BY-SA) | Packaged ingredient nutrition |
| [Food.com via Kaggle](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions) | CSV | Large recipe corpus with user reviews |
| [Hugging Face recipes-with-nutrition](https://huggingface.co/datasets/Shengtao/recipe) | HF Dataset | Recipes pre-paired with nutrition estimates |
| [CulinaryDB](https://cosylab.iiitd.edu.in/culinarydb/) | Research DB | Cuisine-annotated recipe data |
| [Google Places API](https://developers.google.com/maps/documentation/places/web-service) | API | Specialty store geolocation (Houston) |

> **RecipeDB** was considered but not used — coverage and license terms were not adequate for the feature set needed.

### Pipeline Layout

The repository follows a standard data science layout:

```
data/
├── raw/        ← original files, never modified
├── interim/    ← cleaned but not yet feature-engineered
└── processed/  ← final datasets ready for modeling

notebooks/      ← EDA and cleaning notebooks (one per source)
src/            ← pipeline scripts
docs/
├── sources.md          ← provenance for every dataset
├── data_dictionary.md  ← field definitions for processed datasets
└── ethics_privacy.md   ← data ethics and privacy framework
```

### Cleaning Decisions

The major cleaning problems and how they were handled:

| Problem | Decision |
|---------|----------|
| **Missing nutrition** | Drop rows missing calories; use USDA lookup to fill macros where possible |
| **Inconsistent ingredient strings** | Normalize to lowercase, strip quantities/units, map to canonical ingredient names |
| **Duplicates across sources** | Deduplicate on (title, ingredient set) hash |
| **Coarse cuisine labels** | Map all source labels to 5 canonical families + "Other"; manual review for ambiguous cases |
| **Outlier calorie values** | Cap at 5,000 kcal/serving; flag and inspect anything below 10 kcal |

### Feature Engineering

The processed dataset adds three feature groups to every recipe:

1. **Cuisine family label** — one of: Asian, European, Latin American, African, Middle Eastern, Other
2. **Dietary restriction flags** — binary flags: contains_pork, contains_gluten, contains_dairy, is_vegetarian, is_vegan
3. **Nutrition per serving** — calories, protein_g, fat_g, carbs_g, fiber_g

### Ethics and Privacy Framework

Documented in `docs/ethics_privacy.md`:
- **Public/open data only** — no scraping behind authentication walls.
- **API rate limits respected** — USDA and Google Places calls are rate-limited in code.
- **No PII collected** — the pipeline processes recipe data, not user data.
- **Session-based user profile** — when the app collects user preferences, they are stored only in the browser session, not on a server.
- **License compliance** — Food.com data used under Kaggle's terms of service; Open Food Facts under CC BY-SA; attribution maintained in `docs/sources.md`.

---

## Results and Evaluation

This phase produced **clean, feature-engineered datasets** and **documentation artifacts**, not trained models. Key outputs:

| Output | Description |
|--------|-------------|
| `data/processed/recipes_clean.csv` | Unified recipe dataset with cuisine labels and dietary flags |
| `data/processed/nutrition_lookup.csv` | Per-ingredient nutrition table from USDA |
| `docs/sources.md` | Provenance for every dataset |
| `docs/data_dictionary.md` | Field definitions for all processed columns |
| `docs/ethics_privacy.md` | Ethics and privacy commitments |
| EDA notebooks | Distributions, missing-value analysis, label balance charts |

The EDA revealed that cuisine label distribution is imbalanced — Asian and European recipes dominate, African and Middle Eastern recipes are underrepresented. This directly informed the sampling and class-weighting experiments in Phase 03.

---

## Learning Outcomes & Reflection

### What Was Difficult
Ingredient string normalization was significantly harder than anticipated. Free-text ingredients like "2 large cloves of garlic, minced" need to map to a canonical "garlic" for the USDA lookup to work. Building a robust parser for this took far longer than any single modeling step in Phase 03.

Cuisine label assignment for ambiguous recipes (e.g., "Mediterranean" could be European or Middle Eastern; "Tex-Mex" is not purely Latin American) required manual review and documentation of decision rules.

### What Failed or Was Incomplete
- The initial attempt to use USDA's API for all ingredient lookups was too slow for 171,000+ recipes. The pipeline was switched to a local downloaded snapshot of the USDA database.
- RecipeDB was evaluated but not usable at the scale needed. CulinaryDB was a partial substitute but required additional manual labeling.
- The nutrition estimator's training data quality was lower than hoped — the USDA-match pipeline produced some bad matches (e.g., "tomato paste" matching to "almond paste"). This was discovered in Phase 03 and required hand-correcting the top ingredients.

### What You Would Change
- Build the ingredient normalization parser earlier — in Phase 01 as a feasibility test.
- Audit a random sample of USDA matches before writing the full pipeline. The bad matches were systematic and would have been caught by a 100-row spot check.
- Invest more time in African and Middle Eastern recipe sourcing in Phase 02 to reduce the class imbalance discovered at training time.

### Sampling / Evaluation Numbers
Training set sizes (realized in Phase 03, built on this pipeline):
- Cuisine classifier: **63,903** training recipes
- Nutrition estimator: **171,919** training rows
- Origin model: **83,953** training recipes
- Freshness CV model: **~45,000** food photographs

---

## Project Files

| File | Description |
|------|-------------|
| `Phase_02_EverGlow_ITAI_2277.pdf` | Full Phase 02 report (drop into this folder) |
| `README.md` | This file |

> PDF is submitted separately to the LMS. Place it here to make the portfolio self-contained.

**Code and data live in the capstone repository:**
- [`notebooks/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/notebooks) — EDA and cleaning notebooks
- [`docs/sources.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/docs/sources.md) — dataset provenance
- [`docs/data_dictionary.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/docs/data_dictionary.md) — field definitions
- [`docs/ethics_privacy.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/docs/ethics_privacy.md) — ethics framework

---

## Project Structure

```
Phase-02-Data-Pipeline-and-Exploratory-Analysis/
├── README.md
└── Phase_02_EverGlow_ITAI_2277.pdf
```

Data and notebooks are maintained in the capstone repository to avoid duplicating large files.

---

## Dependencies / Requirements

```
pandas>=2.0
numpy>=1.24
matplotlib>=3.7
seaborn>=0.12
requests>=2.31      # USDA API calls
jupyter>=1.0
```

See `requirements.txt` in the [capstone repository](https://github.com/Chloe-Tu2/The-EverFlavor-AI) for the full environment.

---

## Data Access

All data sources are public and free:

| Source | Access |
|--------|--------|
| USDA FoodData Central | [fdc.nal.usda.gov](https://fdc.nal.usda.gov/) — free API key |
| Open Food Facts | [world.openfoodfacts.org](https://world.openfoodfacts.org/) — no auth |
| Food.com / Kaggle | [kaggle.com](https://www.kaggle.com) — free account required |
| Hugging Face | `datasets.load_dataset("Shengtao/recipe")` — no auth |
| CulinaryDB | [cosylab.iiitd.edu.in/culinarydb](https://cosylab.iiitd.edu.in/culinarydb/) — research use |
| Google Places | Requires API key — rate-limited in pipeline |

---

## Course Context

**Course:** ITAI 2277 — Artificial Intelligence Resources & References
**Program:** Applied AI & Robotics, Houston Community College
**Professor:** Anna Devarakonda
**Phase:** 02 of 05 — Data Pipeline and Exploratory Analysis
**Submitted:** October 2, 2026

[← Phase 01](../Phase-01-Capstone-Proposal-and-Problem-Framing/) | [← Back to course folder](../README.md) | [Next: Phase 03 →](../Phase-03-Trained-Models-and-Evaluation/)
