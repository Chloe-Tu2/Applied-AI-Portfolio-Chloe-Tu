# Phase 05 — Final Presentation and Completed Project Package

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Student:** Chloe Tu
> **Submitted:** December 5, 2026 (Final)

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Live_App-FF4B4B?logo=streamlit)](https://everflavor-ai-kitchen.streamlit.app/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Project Overview

Phase 05 is the final packaging and presentation phase. The technical work was done in Phases 01–04. This phase turns that work into **hiring evidence**: a public, navigable portfolio that a stranger can read without help, and a 5-slide employer-facing presentation (`Pf_ChloeTu_ITAI_2277.pdf`) that communicates the full semester arc in under two minutes.

**Presentation PDF:** `Pf_ChloeTu_ITAI_2277.pdf` (submitted to LMS; place in this folder for portfolio completeness)
**Live app:** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)
**Capstone repo:** [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)

---

## Problem Statement

A semester of technical work — six data sources, four trained models, a three-agent CrewAI system, 579 tests, 200+ red-team checks, and a live Streamlit app — means nothing to a hiring manager if they cannot navigate it in a few minutes. The challenge is not technical: it is **communication and structure**.

Specifically:
- How do you write a phase README that is honest about failure without underselling the accomplishment?
- How do you compress a multi-agent system into 5 slides without losing the technical substance?
- How do you make a GitHub folder legible to a stranger who was never in the class?

These are hard problems and they require their own time and iteration.

---

## Approach and Methodology

### Portfolio Packaging

Every phase folder in this course directory contains:
1. A README written for a stranger — no internal shorthand, no assumed context.
2. The original phase PDF report (placed here after LMS submission).
3. Honest reflection on what was difficult, what failed, and what would change.
4. Concrete numbers from the phase reports — not vague claims.

The folder structure is self-explanatory by name. A recruiter who has never heard of ITAI 2277 can navigate from the main README to any phase without asking for context.

### The 5-Slide Presentation

`Pf_ChloeTu_ITAI_2277.pdf` follows the course-required format. See the [Presentation folder](../Presentation/) for the full content outline with slide-by-slide bullets.

| Slide | Topic |
|-------|-------|
| 1 | Introduction — name, AI background, program |
| 2 | Highlights Part 1 — EverFlavor proposal, data pipeline, safety architecture |
| 3 | Highlights Part 2 — four trained models, test suite, live MVP metrics |
| 4 | Real-world applications — dietary compliance, multi-agent RAG, CV for freshness |
| 5 | Wrap-up — GitHub links, live app, contact, additional skills |

### Navigation Path for Recruiters

A stranger can open the live app immediately without reading anything. For technical depth:

1. [Capstone-EverFlavor-AI](../Capstone-EverFlavor-AI/) — Full product summary
2. [Phase-04 MVP](../Phase-04-Integrated-System-Prototype-MVP/) — What was shipped and tested
3. [Phase-03 Models](../Phase-03-Trained-Models-and-Evaluation/) — Training, evaluation, failure analysis
4. [Phase-02 Data](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/) — Pipeline, cleaning, ethics
5. [Phase-01 Proposal](../Phase-01-Capstone-Proposal-and-Problem-Framing/) — Original problem framing
6. `Pf_ChloeTu_ITAI_2277.pdf` — 5-slide executive summary

---

## Results and Evaluation

### What a Recruiter Can Open in Under Two Minutes

| Item | Where |
|------|-------|
| Live app — open in browser, no install | [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/) |
| 5-slide PDF summary | `Pf_ChloeTu_ITAI_2277.pdf` in this folder |
| GitHub code — browse app/, src/, tests/ | [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI) |
| Phase-04 README — MVP test results | [Phase-04 README](../Phase-04-Integrated-System-Prototype-MVP/) |
| Phase-03 README — model numbers | [Phase-03 README](../Phase-03-Trained-Models-and-Evaluation/) |

### Completed Package Checklist

- [x] Public capstone repository with full code and docs
- [x] Live Streamlit app (no login required)
- [x] 5-slide employer presentation PDF
- [x] Phase 01–05 PDFs in matching folders (after LMS submission)
- [x] All README files written for a stranger
- [x] Notes and resources folder with curated links
- [x] Honest reflections in every phase

---

## Learning Outcomes & Reflection

### What Was Difficult
Writing honest reflections is harder than writing accomplishments. The temptation is to frame every problem as "we solved X" — but a hiring manager who actually reads the code will see that the nutrition estimator has ~102 kcal typical error and that the freshness CV model is not integrated into the app UI. Saying that plainly, with the actual numbers, and explaining why, is more credible than omitting it.

Compressing six months of work into 5 slides without losing technical substance required multiple drafts. The constraint is real — a slide that says "we built AI" is useless; a slide that says "cuisine classifier: val accuracy 0.77, macro F1 0.62 on 63,903 training recipes, with safety gate validated against 200+ red-team checks" is evidence.

### What Failed or Was Incomplete
- The freshness CV model (Phase 03: 98.8% produce, 87.4% fish) was not integrated into the app UI — this feature exists as a trained model but has no frontend path in the MVP. It would be the next thing to ship.
- The Houston map is limited to Houston metro. The architecture generalizes to any city with a Places API key, but this was not demonstrated.
- The nutrition estimator's ~102 kcal typical error means the system's calorie feature is an estimate, not a guarantee. The app labels this, but it is a real limitation.

### What You Would Change
- Start the portfolio README drafts in Phase 03, not Phase 05. Waiting until the end creates a time crunch that shows in the writing.
- Record a 2-minute demo video in Phase 04 while the app is freshly built. Adding it to the portfolio after the fact is harder.
- Build the presentation slide structure in Phase 01 (what will slide 3 say?) to guide what numbers to track throughout the project.

### Sampling / Evaluation Numbers
All numbers come from prior phases:
- 579 passed / 26 skipped / 0 failed (Phase 04 test suite, Nov 14, 2026)
- 200+ red-team safety checks (0 failures)
- Cuisine classifier: val acc 0.77, macro F1 0.62
- Nutrition estimator: ~102 kcal typical error
- Origin model: 89.3% on 74.7% of recipes (≥70% confidence)
- Freshness: 98.8% produce, 87.4% fish

---

## Project Files

| File | Description |
|------|-------------|
| `Pf_ChloeTu_ITAI_2277.pdf` | 5-slide employer presentation (drop into this folder after LMS submission) |
| `README.md` | This file |

> The PDF is the official course submission to the LMS. Download your submitted copy and place it here to complete the portfolio.

**All phase reports:**
- [Phase 01](../Phase-01-Capstone-Proposal-and-Problem-Framing/) — `Phase_01_EverGlow_ITAI_2277.pdf`
- [Phase 02](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/) — `Phase_02_EverGlow_ITAI_2277.pdf`
- [Phase 03](../Phase-03-Trained-Models-and-Evaluation/) — `Phase_03_EverGlow_ITAI_2277.pdf`
- [Phase 04](../Phase-04-Integrated-System-Prototype-MVP/) — `Phase_04_EverGlow_ITAI_2277.pdf`

---

## Project Structure

```
Phase-05-Final-Presentation-and-Completed-Project-Package/
├── README.md
└── Pf_ChloeTu_ITAI_2277.pdf
```

---

## Dependencies / Requirements

No new code is introduced in Phase 05. See individual phase folders for their dependencies.

---

## Data Access

No new data is collected in Phase 05. All data artifacts are described in [Phase 02](../Phase-02-Data-Pipeline-and-Exploratory-Analysis/) and [Phase 03](../Phase-03-Trained-Models-and-Evaluation/).

---

## Course Context

**Course:** ITAI 2277 — Artificial Intelligence Resources & References
**Program:** Applied AI & Robotics, Houston Community College
**Professor:** Anna Devarakonda
**Phase:** 05 of 05 — Final Presentation and Completed Project Package
**Due:** December 5, 2026

[← Phase 04](../Phase-04-Integrated-System-Prototype-MVP/) | [← Back to course folder](../README.md)
