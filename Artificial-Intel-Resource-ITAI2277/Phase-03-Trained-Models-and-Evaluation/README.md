# Phase 03 — Trained Models and Evaluation

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Team EverGlow:** Chloe Tu, Eva Abou Abou Harb, Francisco Medina
> **Submitted:** October 26, 2026 (Weeks 7–10)

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn)](https://scikit-learn.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-CV-EE4C2C?logo=pytorch)](https://pytorch.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas)](https://pandas.pydata.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter)](https://jupyter.org)

---

## Project Overview

Phase 03 is the model training and evaluation phase of EverFlavor AI. The system uses a **three-layer architecture**: four trained ML/CV models that handle classification and estimation tasks; local LLM agents that reason over recipe content and answer user questions; and a hard-coded safety gate that sits outside the LLM and cannot be overridden by it. This phase documents what was trained, how each model was evaluated, what failed, and what experiments did not improve results.

> **Important:** The LLM weights were not fine-tuned. The foundation model is used as-is via Ollama. Only the four task-specific models (classifier, estimator, two CV models) were trained from scratch or fine-tuned on the processed data from Phase 02.

**Capstone repository:** [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)
**Live app (Phase 04 result):** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)

---

## Problem Statement

A multi-agent culinary assistant needs four specific predictive capabilities that a general-purpose LLM cannot reliably provide:

1. **Cuisine classification** — which of the five cuisine families does a recipe belong to?
2. **Nutrition estimation** — given a recipe's ingredients and quantities, how many calories per serving?
3. **Geographic origin** — which of 37 countries is this dish most likely from?
4. **Ingredient freshness** — given a photo of a produce item or fish, is it fresh?

Additionally, the LLM agents must answer user questions without hallucinating or making safety decisions. All four of these capabilities require their own training data, training pipeline, and evaluation protocol.

---

## Approach and Methodology

### Three-Layer Architecture

```
Layer 1 — Trained Models
  ├── Cuisine classifier (5 families)
  ├── Nutrition estimator (kcal per serving)
  ├── Origin model (37 countries)
  └── Freshness CV model (produce + fish)

Layer 2 — Local LLM Agents (Ollama)
  ├── Nutritionist & Preference Agent
  ├── Chef Agent
  └── Sourcing Agent

Layer 3 — Code Safety Gate
  └── Hard-coded dietary restriction filter
      (LLM output → gate → user; gate cannot be overridden)
```

### Model Details

#### Cuisine Classifier
- **Task:** Multi-class classification into 5 families (Asian, European, Latin American, African, Middle Eastern) + Other
- **Training data:** 63,903 recipes
- **Features:** TF-IDF on ingredient text + recipe title tokens
- **Framework:** scikit-learn

#### Nutrition Estimator
- **Task:** Regression — calories per serving
- **Training data:** 171,919 recipe-serving pairs
- **Features:** Ingredient vector × USDA nutrition lookup
- **Framework:** scikit-learn

#### Origin Model
- **Task:** Multi-class classification into 37 countries
- **Training data:** 83,953 recipes
- **Confidence threshold:** Only predictions with ≥70% confidence are surfaced (74.7% of recipes pass)
- **Framework:** scikit-learn / Hugging Face

#### Freshness CV Model
- **Task:** Binary classification — fresh vs. not-fresh
- **Training data:** ~45,000 food photographs (produce and fish split)
- **Framework:** PyTorch (CNN fine-tune)

### Safety Gate Design

The safety gate is deterministic Python code — not a prompt, not a classifier, not the LLM. It checks every recipe recommendation against the user's declared restrictions (pork, gluten, dairy, etc.) before it is shown. The LLM never makes the safety decision; it can only generate candidates, which the gate then approves or blocks.

### LLM Agent Testing

Two local Ollama models were tested on 33 factual questions each (66 total test answers). The test evaluated whether agents hallucinate facts, invent safety decisions, or break out of their role.

---

## Results and Evaluation

### Headline Model Performance

| Model | Metric | Value |
|-------|--------|-------|
| **Cuisine classifier** | Val accuracy | 0.77 |
| **Cuisine classifier** | Macro F1 | 0.62 |
| **Nutrition estimator** | Typical error | ~102 kcal |
| **Nutrition estimator** | Within 20% of true | ~30% of estimates |
| **Origin model** | Accuracy (high-confidence slice) | 89.3% |
| **Origin model** | Recipes passing 70% threshold | 74.7% |
| **Origin model** | Countries covered | 37 |
| **Freshness CV — produce** | Test accuracy | 98.8% |
| **Freshness CV — fish** | Test accuracy | 87.4% |
| **LLM agents** | Problems in 66 test answers | 0 |

### Failures Fixed During This Phase

| Problem | Fix |
|---------|-----|
| Bad USDA matches (e.g. "tomato paste" ↔ "almond paste") | Hand-matched the top 200 ingredients; re-ran nutrition pipeline |
| Fish freshness model — weak training epoch; macro F1 0.60 | Retrained with corrected epoch schedule; F1 rose to 0.87 |
| Safety gate missed 31 tricky dish names (e.g. dishes containing pork but named without "pork") | Added hand-curated list; expanded gate logic |
| LLM tool-loop bug — agents occasionally called tools in an infinite loop | Fixed in agent orchestration code |
| Calorie-per-serving calculation bug — was computing per-100g, not per-serving | Fixed unit conversion in the estimator pipeline |

### Experiments That Did Not Help

- **Upweighting rare cuisine classes** (African, Middle Eastern) in the cuisine classifier — this hurt overall macro F1 and was reverted.
- **Upweighting rare countries** in the origin model — same result; reverted.

The class imbalance problem is real, but naive upweighting made it worse. Better data sourcing (Phase 02) would be the right long-term fix.

---

## Learning Outcomes & Reflection

### What Was Difficult
The nutrition estimator was the hardest model to build. The ground-truth label (calories per serving) is itself uncertain — serving sizes are not standardized across recipes, and the USDA calorie values for the same ingredient vary by preparation method. Getting the estimator to a typical error of ~102 kcal required significant pipeline work, not just model tuning.

The freshness CV model for fish was the second hardest. Fish appearance varies by species, lighting, and preparation stage in ways that produce does not. The first training run produced macro F1 0.60 on fish; retraining to 0.87 required correcting the training epoch and adding more species-diverse samples.

Understanding when **not** to use a model (the origin model's confidence threshold) was a key conceptual lesson — it is better to abstain than to output a wrong country.

### What Failed or Was Incomplete
- The nutrition estimator's ~102 kcal typical error and ~30% within-20% rate are weaker than hoped. A production system would want these tighter. The root cause is noisy training labels (inconsistent serving size definitions), not model architecture.
- Upweighting rare classes was tried twice and failed both times — a known-bad idea in retrospect, but it took real experiments to confirm.
- The origin model only covers 37 countries. Many cuisine families (especially African) have fewer than 10 country-level training samples; the model abstains on most African recipes rather than guessing.

### What You Would Change
- Invest in better training data for the nutrition estimator before training any model — the ~102 kcal error is a data problem, not a modeling problem.
- Run a preliminary USDA-match audit (100 random samples) before writing the full pipeline. The almond/tomato paste bug would have been caught immediately.
- Add an abstention rate metric to the cuisine classifier as well — predicting "Other" with high confidence is more useful than a low-confidence wrong label.

### Sampling / Evaluation Numbers (All from this phase)
- Cuisine: 63,903 train / held-out test set; val acc 0.77, macro F1 0.62
- Nutrition: 171,919 train rows; ~102 kcal typical error; ~30% within 20%
- Origin: 83,953 train; 89.3% on 74.7% of recipes (≥70% confidence); 37 countries
- Freshness: ~45,000 photos; 98.8% produce, 87.4% fish
- LLM: 33 questions × 2 models = 66 answers; 0 problems

---

## Project Files

| File | Description |
|------|-------------|
| `Phase_03_EverGlow_ITAI_2277.pdf` | Full Phase 03 report (drop into this folder) |
| `README.md` | This file |

> PDF is submitted separately to the LMS. Place it here to make the portfolio self-contained.

**Code lives in the capstone repository:**
- [`notebooks/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/notebooks) — Training and evaluation notebooks
- [`src/everflavor/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/src/everflavor) — Safety gate, calorie calculator, estimators

---

## Project Structure

```
Phase-03-Trained-Models-and-Evaluation/
├── README.md
└── Phase_03_EverGlow_ITAI_2277.pdf
```

Models and notebooks are maintained in the capstone repository.

---

## Dependencies / Requirements

```
scikit-learn>=1.3
torch>=2.0
torchvision>=0.15
transformers>=4.35    # Hugging Face tokenizers
pandas>=2.0
numpy>=1.24
matplotlib>=3.7
jupyter>=1.0
ollama                # local LLM serving
```

See `requirements.txt` in the [capstone repository](https://github.com/Chloe-Tu2/The-EverFlavor-AI) for the pinned environment.

---

## Data Access

Training data was produced by the Phase 02 pipeline:
- Cuisine / origin / nutrition datasets: `data/processed/` in the capstone repo
- Freshness photos: ~45,000 images collected from public food photography datasets
- USDA and Open Food Facts: see [Phase 02 data sources](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/README.md#data-access)

---

## Course Context

**Course:** ITAI 2277 — Artificial Intelligence Resources & References
**Program:** Applied AI & Robotics, Houston Community College
**Professor:** Anna Devarakonda
**Phase:** 03 of 05 — Trained Models and Evaluation
**Submitted:** October 26, 2026

[← Phase 02](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/) | [← Back to course folder](../README.md) | [Next: Phase 04 →](../Phase-04-Integrated-System-Prototype-MVP/)
