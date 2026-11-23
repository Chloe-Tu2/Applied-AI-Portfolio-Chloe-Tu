# Capstone — EverFlavor AI

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Team EverGlow:** Chloe Tu, Eva Abou Abou Harb, Francisco Medina
> **Professor:** Anna Devarakonda · **Term:** Fall 2026

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Live_App-FF4B4B?logo=streamlit)](https://everflavor-ai-kitchen.streamlit.app/)
[![CrewAI](https://img.shields.io/badge/CrewAI-Multi--Agent-6C63FF)](https://github.com/joaomdmoura/crewAI)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn)](https://scikit-learn.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-CV-EE4C2C?logo=pytorch)](https://pytorch.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas)](https://pandas.pydata.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Project Overview

**EverFlavor AI** is a live, conversational multi-agent system that recommends authentic global recipes matched to a user's remaining calorie budget, dietary restrictions, and local ingredient availability. It was designed and built across a full semester by Team EverGlow as the capstone for ITAI 2277.

> 🌐 **Try it now:** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)
> 💻 **Full codebase:** [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)

This README summarizes the full product arc — from proposal through live deployment — using concrete numbers from each phase. It is the recommended starting point for anyone who wants to understand the system before reading the phase-specific details.

---

## Problem Statement

A user says: *"I have 550 calories left, no pork, I'm tired after work, and I want something bold from Middle Eastern or Latin American cuisine. I can drive 15 minutes."* No existing recipe app handles this as a single, unified request.

The problem has three interlocked parts:
1. **Calorie and restriction filtering** — the system must enforce dietary constraints reliably, not probabilistically. A gluten or pork restriction is a safety constraint, not a preference.
2. **Authentic cuisine matching** — recommendations should come from the actual culinary traditions of the requested region, not Westernized approximations.
3. **Local sourcing** — specialty ingredients must be findable within a realistic driving radius for the system to be useful.

The four user personas the system serves: busy professional, impatient foodie, overworked parent, efficiency-focused single/student.

---

## Approach and Methodology

### Multi-Agent Architecture

The system is orchestrated by **CrewAI** with three cooperating agents:

| Agent | Role |
|-------|------|
| **Nutritionist & Preference Agent** | Parses calorie budget, dietary restrictions, cuisine preference, and effort level from the user's natural-language request |
| **Chef Agent** | Retrieves and ranks candidate recipes matching the nutritional and flavor criteria across five cuisine families |
| **Sourcing Agent** | Finds the nearest specialty store within the user's drive radius carrying required specialty ingredients (Houston metro) |

### Three-Layer System Design

```
Layer 1 — Trained ML/CV Models
  ├── Cuisine classifier  (5 families, val acc 0.77, macro F1 0.62)
  ├── Nutrition estimator (typical error ~102 kcal)
  ├── Origin model        (89.3% on 74.7% of recipes, 37 countries)
  └── Freshness CV        (98.8% produce, 87.4% fish)

Layer 2 — Local LLM Agents (Ollama)
  ├── CrewAI planner
  ├── Tool-calling agents with restricted tool set
  └── Walter & Nathalie (waiter agents; sourced knowledge only)

Layer 3 — Code Safety Gate (DETERMINISTIC — LLM cannot override)
  └── Checks every recommendation against the user's declared restrictions
      before anything is shown; validated against 200+ red-team checks
```

> **Safety is code, not the LLM.** The gate is deterministic Python. The LLM has no path to override it. This was a deliberate design decision from Phase 01 and carried through every subsequent phase.

### Data Foundation

Six public data sources, cleaned and unified into a processed dataset of 291,755 recipes (61.8% with photos):

| Source | Use |
|--------|-----|
| USDA FoodData Central | Ground-truth nutrition per ingredient |
| Open Food Facts | Packaged ingredient nutrition |
| Food.com via Kaggle | Large recipe corpus (63,903 cuisine training recipes) |
| Hugging Face recipes-with-nutrition | Pre-paired nutrition estimates |
| CulinaryDB | Cuisine-annotated data |
| Wikipedia / Wikidata | 4,885 dish entries for waiter knowledge base |

### Waiter Agent Knowledge (Walter & Nathalie)

The waiter agents answer sourcing and dish-background questions using **only sourced facts**:
- 4,885 dish entries from Wikipedia / Wikidata
- 71 injection test questions evaluated — 0 invented facts, 0 safety decisions by LLM
- Structured retrieval, not open-ended generation
- If a dish is not in the knowledge base, the agent says so

### Privacy Model

- **No server-side user database.** The user's dietary profile and cookbook are stored only in their browser session.
- Session-only user profile — cleared when the browser tab closes.
- Optional browser-only cookbook for saving favorite recipes.
- No PII collected at any point.

---

## Results and Evaluation

### Live Application

The MVP is deployed on Streamlit Community Cloud and publicly accessible:

| Feature | Status |
|---------|--------|
| Find Recipes (calorie + restriction + cuisine query) | ✅ Live |
| Search by Country / Dish | ✅ Live (37 countries, 4,885 dishes) |
| Check My Recipe | ✅ Live |
| Houston Map (specialty stores) | ✅ Live |
| 7 Kitchens + Pixel Chef UI | ✅ Live |
| Waiter Agents (Walter & Nathalie) | ✅ Live |
| Profile & Browser-only Cookbook | ✅ Live |
| Freshness CV (photo upload) | 🔶 Model trained, UI not yet shipped |

### Test Suite

| Metric | Value |
|--------|-------|
| Test functions | 314 |
| Test files | 37 |
| Passed (Nov 14 clean run) | 579 |
| Skipped | 26 |
| Failed | 0 |
| Red-team safety checks | 200+ |
| Waiter injection tests | 71 |

### Model Performance

| Model | Key Metric |
|-------|------------|
| Cuisine classifier | Val acc 0.77 · Macro F1 0.62 (63,903 train recipes) |
| Nutrition estimator | ~102 kcal typical error (171,919 train rows) |
| Origin model | 89.3% on 74.7% of recipes (83,953 train; 37 countries) |
| Freshness CV | 98.8% produce · 87.4% fish (~45,000 photos) |

---

## Learning Outcomes & Reflection

### What Was Difficult
The nutrition estimator's error rate (~102 kcal) reflects a fundamental data problem: serving size definitions are not standardized across recipe databases, and USDA calorie values vary by ingredient preparation method. No model architecture can fix inconsistent ground truth — this was the hardest lesson of the project.

Keeping the safety gate comprehensive required constant vigilance. By Phase 04, 31 tricky dish names had been added to the gate manually — dishes whose names do not contain "pork" but whose canonical recipes do. This kind of edge-case enumeration is never finished.

### What Failed or Was Incomplete
- The freshness CV model (98.8% produce, 87.4% fish) is trained and evaluated but not integrated into the app UI. It is the clearest gap between "model exists" and "feature shipped."
- The nutrition estimator carries ~102 kcal typical error. Only ~30% of estimates fall within 20% of the true value. The app displays estimates with appropriate uncertainty labeling, but this is a real limitation.
- Upweighting rare cuisine classes (African, Middle Eastern) in training made classification worse, not better. The underlying problem is insufficient data for these families, not a weighting issue.

### What You Would Change
- Invest more in data quality before training. The USDA-match bug (tomato paste ↔ almond paste) was caught only in Phase 03 and required a full pipeline re-run.
- Build the safety gate architecture before the UI. Retrofitting it into a multi-page Streamlit app was the most expensive refactor of Phase 04.
- Write integration tests during Phase 03, not at the end of Phase 04.

### Key Numbers

| Metric | Value |
|--------|-------|
| Recipes in processed dataset | 291,755 |
| Recipes with photo | 61.8% (was ~24% before enrichment) |
| Dish knowledge entries | 4,885 |
| Red-team checks passed | 200+ / 200+ |
| App test suite | 579 passed, 0 failed |

---

## Project Files

This folder is a summary layer. All code and data live in the capstone repository.

| Resource | Link |
|----------|------|
| **Full codebase** | [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI) |
| **Live app** | [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/) |
| **App pages** | [`app/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/app) |
| **Backend safety + agents** | [`src/everflavor/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/src/everflavor) |
| **Training notebooks** | [`notebooks/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/notebooks) |
| **Data documentation** | [`docs/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/docs) |
| **Data sources** | [`docs/sources.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/docs/sources.md) |
| **Project governance** | [`GOVERNANCE.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/GOVERNANCE.md) |
| **Security policy** | [`SECURITY.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/SECURITY.md) |

**Phase reports:**
- [Phase 01 — Proposal](../Phase-01-Capstone-Proposal-and-Problem-Framing/)
- [Phase 02 — Data Pipeline](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/)
- [Phase 03 — Models](../Phase-03-Trained-Models-and-Evaluation/)
- [Phase 04 — MVP](../Phase-04-Integrated-System-Prototype-MVP/)
- [Phase 05 — Presentation](../Phase-05-Final-Presentation-and-Completed-Project-Package/)

---

## Project Structure

```
Capstone-EverFlavor-AI/
└── README.md           ← This file (summary layer)

External capstone repository:
The-EverFlavor-AI/
├── app/                ← Streamlit pages and UI
├── src/everflavor/     ← Safety gate, recommender, agents, tools
├── notebooks/          ← Training and EDA notebooks
├── data/               ← raw / interim / processed datasets
├── docs/               ← sources.md, data_dictionary.md, ethics_privacy.md
├── GOVERNANCE.md
├── SECURITY.md
└── requirements.txt
```

---

## Dependencies / Requirements

```
streamlit>=1.28
crewai>=0.1
scikit-learn>=1.3
torch>=2.0
torchvision>=0.15
transformers>=4.35
pandas>=2.0
numpy>=1.24
ollama
pytest>=7.4
```

Full pinned environment: [`requirements.txt`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/requirements.txt) in the capstone repo.

---

## Data Access

| Data | Access |
|------|--------|
| USDA FoodData Central | [fdc.nal.usda.gov](https://fdc.nal.usda.gov/) — free API key |
| Open Food Facts | [world.openfoodfacts.org](https://world.openfoodfacts.org/) — no auth (CC BY-SA) |
| Food.com / Kaggle | [kaggle.com](https://www.kaggle.com) — free account |
| Hugging Face | `datasets.load_dataset("Shengtao/recipe")` |
| CulinaryDB | [cosylab.iiitd.edu.in/culinarydb](https://cosylab.iiitd.edu.in/culinarydb/) |
| Wikipedia / Wikidata | Public API — no auth |

---

## Course Context

**Course:** ITAI 2277 — Artificial Intelligence Resources & References
**Program:** Applied AI & Robotics, Houston Community College
**Professor:** Anna Devarakonda
**Team:** EverGlow — Chloe Tu, Eva Abou Abou Harb, Francisco Medina
**Term:** Fall 2026

[← Back to course folder](../README.md)
