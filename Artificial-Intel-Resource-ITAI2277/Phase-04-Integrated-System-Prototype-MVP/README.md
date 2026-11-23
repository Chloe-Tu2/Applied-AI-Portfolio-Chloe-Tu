# Phase 04 — Integrated System Prototype / MVP

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Team EverGlow:** Chloe Tu, Eva Abou Abou Harb, Francisco Medina
> **Submitted:** November 16, 2026 (Weeks 11–13)

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Live_App-FF4B4B?logo=streamlit)](https://everflavor-ai-kitchen.streamlit.app/)
[![CrewAI](https://img.shields.io/badge/CrewAI-Multi--Agent-6C63FF)](https://github.com/joaomdmoura/crewAI)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn)](https://scikit-learn.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-CV-EE4C2C?logo=pytorch)](https://pytorch.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Project Overview

Phase 04 integrated all prior work — data pipeline, trained models, LLM agents, and safety gate — into a live, publicly accessible MVP: **EverFlavor Kitchen**, deployed on Streamlit Community Cloud. This is the deliverable that a stranger can open in a browser right now and use.

🌐 **Live app:** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)
💻 **Code:** [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)

The test suite reached **579 passed, 26 skipped, 0 failed** (clean run November 14, 2026) across 314 test functions in 37 files. The safety gate was validated against **200+ red-team adversarial checks**.

---

## Problem Statement

Having four trained models, a CrewAI multi-agent planner, and a safety gate is not a product. The integration challenge is real and distinct from training: models must serve in milliseconds, agents must coordinate without deadlocking, the safety gate must intercept every code path that could reach the user, and the full system must be testable, deployable, and usable by someone who has never seen the code.

Additionally, the UI must communicate the system's safety guarantees and uncertainty without overwhelming a non-technical user. A recipe recommendation is useless if the user cannot trust that their dietary restriction was actually enforced.

---

## Approach and Methodology

### Application Architecture

```
User Browser (Streamlit)
    │
    ▼
app/                        ← Streamlit pages and UI components
    ├── Home / Kitchen
    ├── Find Recipes
    ├── Search by Country or Dish
    ├── Check My Recipe
    ├── Dish Page
    ├── Houston Map
    ├── Profile & Cookbook
    └── What's New (bell)

src/everflavor/             ← Backend logic
    ├── safety_gate.py      ← Hard-coded dietary filter (LLM cannot override)
    ├── recommender.py      ← Recipe ranking pipeline
    ├── calorie_calc.py     ← Per-serving calorie calculator
    ├── time_estimator.py   ← Cooking time estimator
    ├── agent_tools.py      ← Tools available to CrewAI agents
    ├── answer_guard.py     ← Post-generation answer validator
    └── crew_planner.py     ← CrewAI agent orchestration
```

### Key Features Shipped in MVP

| Feature | Description |
|---------|-------------|
| **First-visit safety profile** | User declares restrictions (pork, gluten, dairy, etc.) before any recipe is served |
| **Find Recipes** | Conversational calorie + restriction + cuisine query; agents plan, chef selects, gate approves |
| **Search by Country / Dish** | Browse 37 countries and 4,885 sourced dish entries |
| **Check My Recipe** | User pastes any recipe; system checks it against their safety profile |
| **Dish Page** | Per-dish detail: origin, nutrition estimate, freshness tips |
| **Houston Map** | Interactive map of specialty stores within driving radius |
| **7 Kitchens + Pixel Chefs** | UI theming — one visual kitchen per cuisine family |
| **Waiters Walter & Nathalie** | Conversational agents for sourcing questions; knowledge sourced from Wikipedia/Wikidata only; never invent facts; never decide safety |
| **Profile & Cookbook** | User can save favorite recipes; cookbook stored in browser only — no server-side user database |
| **What's New Bell** | Changelog UI for new features |
| **Beta Label** | Prominent label — users know the system is not yet production-validated |

### Safety Architecture

The safety gate is **deterministic Python code**, not an LLM prompt:
- Checks every recipe against the user's declared restrictions before display.
- Validated against **200+ red-team adversarial checks** (tricky dish names, edge-case ingredients, injection attempts).
- 71 injection test questions validated against waiter agents — agents never invent facts, never decide safety.
- The LLM has no path to override the gate.

### Waiter Agent Knowledge Base

Walter and Nathalie (the sourcing/storytelling waiter agents) draw facts exclusively from:
- **4,885 dish entries** from Wikipedia and Wikidata
- Structured retrieval — no open-ended generation of facts
- If a dish is not in the knowledge base, the agent says so rather than generating an answer

### Photos

61.8% of the 291,755 recipes in the processed dataset have a photo (up from ~24% in the initial data pipeline). Photo enrichment was done by matching recipes to public food photography datasets.

### Test Suite

| Metric | Value |
|--------|-------|
| Test functions | 314 |
| Test files | 37 |
| Passed (clean run Nov 14) | 579 |
| Skipped | 26 |
| Failed | 0 |
| Red-team safety checks | 200+ |
| Waiter injection tests | 71 |

---

## Results and Evaluation

The MVP is live and publicly accessible. A recruiter can open it right now without installing anything.

**What works:**
- End-to-end recipe recommendation with calorie + restriction filtering.
- Safety gate blocks every adversarial case in the red-team suite (200+ checks, 0 failures).
- Waiter agents answer sourcing questions using only sourced facts.
- Houston map shows specialty stores within user-specified drive radius.
- Cookbook saves and restores across sessions in the same browser.

**What is labeled Beta / known limitations:**
- Nutrition estimates carry ~102 kcal typical error (inherited from Phase 03 model).
- Origin model abstains on 25.3% of recipes (confidence below 70% threshold) — these recipes show "origin unknown" rather than a wrong answer.
- The system is scoped to Houston for the geolocation feature.
- Waiter knowledge covers 4,885 dishes — gaps exist for rare regional dishes.

---

## Learning Outcomes & Reflection

### What Was Difficult
Integration is harder than training. Getting the safety gate to intercept every code path that could serve a recipe took multiple refactors — the app has more UI entry points than the backend originally accounted for (direct URL navigation, search, check-my-recipe, waiter chat).

The test suite (579 tests, 37 files) was not originally planned at this scale. It grew as edge cases were discovered. Writing tests for a UI with LLM-backed agents required careful mocking so tests are deterministic and fast.

Waiter agent scope management was unexpectedly difficult. The agents kept finding ways to drift from sourced knowledge into generation. The answer guard (`answer_guard.py`) was added specifically to intercept this.

### What Failed or Was Incomplete
- The Houston Map feature uses approximate store data — real-time Google Places API calls are rate-limited and not available for every cuisine family.
- The "Check My Recipe" feature analyzes text-based recipes only; photo-upload recipe checking was prototyped but not shipped in this MVP.
- The freshness CV model (Phase 03) is not yet integrated into the main app flow — it was built and evaluated but the UI for uploading a food photo is not in the MVP.

### What You Would Change
- Design the safety gate's intercept architecture before writing any UI code — retrofitting it was the most expensive refactor in the phase.
- Scope the waiter knowledge base earlier and build the answer guard in Phase 03, not Phase 04.
- Write integration tests in Phase 03 so the Phase 04 test suite starts at a baseline rather than from zero.

### Sampling / Evaluation Numbers
- 579 tests passed on a clean run (Nov 14, 2026)
- 200+ red-team safety checks: 0 failures
- 71 waiter injection tests: 0 invented facts, 0 safety decisions by LLM
- 61.8% of 291,755 recipes have a photo
- 4,885 dish entries in waiter knowledge base

---

## Project Files

| File | Description |
|------|-------------|
| `Phase_04_EverGlow_ITAI_2277.pdf` | Full Phase 04 report (drop into this folder) |
| `README.md` | This file |

> PDF is submitted separately to the LMS. Place it here to make the portfolio self-contained.

**Live code and app:**
- **Live app:** [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)
- [`app/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/app) — Streamlit pages
- [`src/everflavor/`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/tree/main/src/everflavor) — Backend safety gate, recommender, agents
- [`GOVERNANCE.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/GOVERNANCE.md) — Project governance
- [`SECURITY.md`](https://github.com/Chloe-Tu2/The-EverFlavor-AI/blob/main/SECURITY.md) — Security policy

---

## Project Structure

```
Phase-04-Integrated-System-Prototype-MVP/
├── README.md
└── Phase_04_EverGlow_ITAI_2277.pdf
```

Full application code lives in the capstone repository.

---

## Dependencies / Requirements

```
streamlit>=1.28
crewai>=0.1
scikit-learn>=1.3
torch>=2.0
pandas>=2.0
numpy>=1.24
ollama                 # local LLM serving
pytest>=7.4            # 314 test functions
```

See `requirements.txt` in the [capstone repository](https://github.com/Chloe-Tu2/The-EverFlavor-AI) for the full pinned environment.

---

## Data Access

- **Recipes:** 291,755 processed recipes (61.8% with photo) — from Phase 02 pipeline
- **Dish knowledge base:** 4,885 entries from Wikipedia / Wikidata (see `docs/sources.md` in the capstone repo)
- **Store geolocation:** Google Places API, Houston metro only
- **User data:** No server-side database; cookbook is browser-only (localStorage)

---

## Course Context

**Course:** ITAI 2277 — Artificial Intelligence Resources & References
**Program:** Applied AI & Robotics, Houston Community College
**Professor:** Anna Devarakonda
**Phase:** 04 of 05 — Integrated System Prototype / MVP
**Submitted:** November 16, 2026

[← Phase 03](../Phase-03-Trained-Models-and-Evaluation/) | [← Back to course folder](../README.md) | [Next: Phase 05 →](../Phase-05-Final-Presentation-and-Completed-Project-Package/)
