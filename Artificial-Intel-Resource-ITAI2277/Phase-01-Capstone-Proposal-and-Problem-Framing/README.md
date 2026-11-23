# Phase 01 — Capstone Proposal and Problem Framing

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Team EverGlow:** Chloe Tu, Eva Abou Abou Harb, Francisco Medina
> **Submitted:** September 10, 2026 (Week 3)

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![CrewAI](https://img.shields.io/badge/CrewAI-Multi--Agent-6C63FF)](https://github.com/joaomdmoura/crewAI)
[![Streamlit](https://img.shields.io/badge/Streamlit-Planned-FF4B4B?logo=streamlit)](https://streamlit.io)

---

## Project Overview

Phase 01 is the formal proposal and problem-framing document for **EverFlavor AI**, a conversational multi-agent system that recommends authentic global recipes matched to a user's remaining calorie budget, dietary restrictions, and local ingredient availability — including the nearest specialty grocery store. The proposal defines the problem, the user personas the system serves, the three-agent architecture, the planned technology stack, and the human-in-the-loop (HITL) safety model.

**Capstone repository:** [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)
**Live app (Phase 04 result):** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)

---

## Problem Statement

Millions of people want to eat authentically from global cuisines while staying within health constraints — calorie limits, allergen avoidance, ingredient availability — but existing recipe apps treat these as separate problems. A busy parent or tired professional cannot easily ask a single system: *"I have 550 calories left, no pork, I'm tired after work, and I want something bold from Middle Eastern or Latin American cuisine. I can drive 15 minutes."*

The proposal identified four primary user personas:
- **Busy professional** — needs fast, specific answers; no time to browse.
- **Impatient foodie** — wants bold, authentic flavors; resents watered-down suggestions.
- **Overworked parent** — dietary restrictions for multiple family members; needs confidence in safety.
- **Efficiency-focused single or student** — minimizes waste; shops once per week; calorie-tracks.

No existing app handles calorie budget + restriction filtering + authentic cuisine + local sourcing in one conversational interface.

---

## Approach and Methodology

### Architecture: Three Cooperating Agents

The proposal defined a three-agent architecture orchestrated by CrewAI:

| Agent | Role |
|-------|------|
| **Nutritionist & Preference Agent** | Parses calorie budget, dietary restrictions, cuisine preference, effort level from the user's natural-language request |
| **Chef Agent** | Retrieves and ranks candidate recipes matching the nutritional and flavor criteria |
| **Sourcing Agent** | Finds the nearest specialty store (within a user-specified drive radius) carrying the required specialty ingredients |

### Safety Model

A **hard-coded post-generation safety filter** sits between the LLM output and the user. The LLM cannot override it. This was a deliberate design decision: dietary restrictions (no pork, no gluten) are safety constraints, not preferences, and cannot be delegated to probabilistic reasoning. Human-in-the-loop touchpoints:
- User reviews the safety gate result before the recipe is confirmed.
- User can accept or reject ingredient substitutions in the chat.

### Planned Tech Stack

| Component | Technology |
|-----------|------------|
| Agent orchestration | CrewAI |
| Frontend (initial plan) | Gradio (later migrated to Streamlit) |
| Nutrition data | USDA FoodData Central, Open Food Facts |
| Recipe data | Food.com (Kaggle), Hugging Face recipes-with-nutrition |
| Geolocation | Google Places API (single metro: Houston) |
| LLM | Tool-calling LLM (local via Ollama) |

### Cuisine Scope

Five cuisine families were scoped for the initial system:
**Asian · European · Latin American · African · Middle Eastern**

---

## Results and Evaluation

This phase produced a **proposal document and slide deck**, not a trained system. The deliverable was reviewed by the instructor for:
- Clarity of problem framing
- Feasibility of the three-agent architecture
- Adequacy of the safety model
- Realism of the data plan

The proposal was approved to proceed to Phase 02. The core architecture (three agents, hard-coded safety gate, five cuisine families) survived intact through all subsequent phases. The only tech change was replacing Gradio with Streamlit.

---

## Learning Outcomes & Reflection

### What Was Difficult
Defining the boundary between what the LLM should decide and what must be hard-coded was harder than expected. The natural instinct is to let the model handle everything — but the proposal forced a clear argument for why dietary safety must be code, not prompting. Writing that argument precisely was valuable and carried through all subsequent phases.

Scoping the sourcing agent to a single metro (Houston) was also a difficult tradeoff to defend — the system is less general but significantly more reliable and testable.

### What Failed or Was Incomplete
- The initial proposal assumed Gradio would be sufficient for the frontend. By Phase 04, Streamlit was used instead — Gradio's stateful multi-page limitations became apparent only when building.
- The proposal did not fully anticipate the data cleaning burden in Phase 02; the assumption that Open Food Facts and USDA data would be "ready to use" proved optimistic.

### What You Would Change
- Add a data quality audit step to the proposal phase before committing to specific sources.
- Define the safety gate logic more formally in the proposal — by Phase 03, 31 tricky dish names had to be manually added because the original definition was too coarse.

### Sampling / Evaluation Numbers
Phase 01 had no quantitative metrics — it was a design document. Concrete numbers begin in Phase 03.

---

## Project Files

| File | Description |
|------|-------------|
| `Phase_01_EverGlow_ITAI_2277.pdf` | Full written proposal report (drop into this folder) |
| `Capstone-Project-Proposal_Slides_EverGlow_ITAI_2277.pdf` | Proposal slide deck (drop into this folder) |
| `README.md` | This file |

> **Note:** PDF files are submitted separately to the LMS. Download from the course submission and place them in this folder to make the portfolio self-contained.

---

## Project Structure

```
Phase-01-Capstone-Proposal-and-Problem-Framing/
├── README.md
├── Phase_01_EverGlow_ITAI_2277.pdf
└── Capstone-Project-Proposal_Slides_EverGlow_ITAI_2277.pdf
```

---

## Dependencies / Requirements

No code was produced in Phase 01. The proposal is a planning document. All implementation begins in Phase 02.

---

## Data Access

No data was collected or processed in Phase 01. Data sources were identified and justified in the proposal:
- [USDA FoodData Central](https://fdc.nal.usda.gov/) — public, no auth required
- [Open Food Facts](https://world.openfoodfacts.org/) — open database, CC BY-SA
- [Food.com dataset on Kaggle](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions) — requires free Kaggle account
- [Hugging Face recipes-with-nutrition](https://huggingface.co/datasets/Shengtao/recipe) — public

---

## Course Context

**Course:** ITAI 2277 — Artificial Intelligence Resources & References
**Program:** Applied AI & Robotics, Houston Community College
**Professor:** Anna Devarakonda
**Phase:** 01 of 05 — Capstone Proposal and Problem Framing
**Submitted:** September 10, 2026

[← Back to course folder](../README.md) | [Next: Phase 02 →](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/)
