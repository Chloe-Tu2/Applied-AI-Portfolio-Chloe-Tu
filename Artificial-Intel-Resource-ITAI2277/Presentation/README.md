# Presentation — Pf_ChloeTu_ITAI_2277

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Student:** Chloe Tu · **Term:** Fall 2026
> **File submitted to LMS:** `Pf_ChloeTu_ITAI_2277.pdf`

---

## Purpose of This Folder

The course required a 5-slide employer-facing presentation submitted as a PDF (`Pf_ChloeTu_ITAI_2277.pdf`) to the LMS. This folder documents the full content of that presentation so the portfolio is self-contained for anyone reading it on GitHub — no need to download the PDF to understand what it covers.

> **Drop the PDF here:** After submitting to the LMS, download your copy and place `Pf_ChloeTu_ITAI_2277.pdf` in this folder.

---

## Slide-by-Slide Content Outline

### Slide 1 — Introduction

**Goal:** Establish who you are and what AI background you bring to the conversation.

Suggested content:
- **Name:** Chloe Tu
- **Program:** Applied AI & Robotics, Houston Community College
- **Course:** ITAI 2277 — Artificial Intelligence Resources & References
- **Brief expertise summary:**
  - Multi-agent system design and orchestration (CrewAI)
  - ML model training, evaluation, and honest failure analysis
  - Safety-first AI design — deterministic gates, not LLM-delegated decisions
  - End-to-end deployment: from raw data to live Streamlit app
  - Full-semester capstone: EverFlavor AI, a live conversational culinary assistant

---

### Slide 2 — Highlights Part 1: Problem Framing, Data, and Safety Architecture

**Goal:** Show you can define a real problem, source and clean data at scale, and design a safety system that works.

Suggested bullets:

**What was built:**
- EverFlavor AI — multi-agent system for authentic global recipe recommendations under calorie + dietary constraints + local sourcing
- Example query: *"550 calories left, no pork, something bold from Middle Eastern or Latin American cuisine, can drive 15 min"*

**Data pipeline (Phase 02):**
- 6 public data sources: USDA FoodData Central, Open Food Facts, Food.com (Kaggle), Hugging Face recipes-with-nutrition, CulinaryDB, Wikipedia/Wikidata
- 291,755 processed recipes; 61.8% with photos (up from ~24%)
- Features: 5 cuisine family labels, 5 dietary restriction flags, nutrition per serving

**Safety architecture:**
- Hard-coded Python gate intercepts every recommendation before it reaches the user
- LLM cannot override the gate — dietary restrictions are enforced by code
- Validated against 200+ red-team adversarial checks: 0 failures

---

### Slide 3 — Highlights Part 2: Trained Models and Live MVP

**Goal:** Show concrete ML results and a shipped product — not just notebooks.

Suggested bullets:

**Four trained models (Phase 03):**

| Model | Key Result |
|-------|------------|
| Cuisine classifier | Val accuracy 0.77 · Macro F1 0.62 (63,903 train recipes) |
| Nutrition estimator | ~102 kcal typical error (171,919 train rows) |
| Origin model | 89.3% on 74.7% of recipes (83,953 train; 37 countries) |
| Freshness CV | 98.8% produce · 87.4% fish (~45,000 photos) |

**Live MVP (Phase 04):**
- Deployed: [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)
- 7 cuisine-themed kitchens; Houston specialty store map
- 4,885 dish entries (Wikipedia/Wikidata); waiter agents never invent facts
- Test suite: **579 passed, 26 skipped, 0 failed** (Nov 14, 2026 clean run; 314 functions in 37 files)
- Privacy: no server-side user database; cookbook is browser-only

**Honest limitation to name on the slide:**
- Nutrition estimator carries ~102 kcal typical error — a data quality problem, not a modeling problem; labeled in the app

---

### Slide 4 — Real-World Applications

**Goal:** Connect the technical skills demonstrated in the capstone to industries and job functions a hiring manager cares about.

Suggested content:

**Where these skills apply:**

| Skill Demonstrated | Real-World Application |
|--------------------|------------------------|
| Multi-agent orchestration (CrewAI) | Healthcare: patient intake routing agents; finance: multi-step compliance review |
| Safety-by-code (deterministic gate) | Any regulated domain — medical device software, legal AI, financial recommendation |
| Nutrition/diet ML | Hospital nutrition compliance, fitness app personalization, corporate wellness |
| Computer vision for freshness | Supply-chain quality control, restaurant inventory management, food safety inspection |
| Privacy-preserving design (no server DB) | GDPR/CCPA-compliant SaaS; enterprise HR tools; consumer health apps |
| Hyperlocal recommendation | Retail inventory + location; event discovery; on-demand services |

**Industries ready to hire this skill set:**
- Healthcare technology and digital health
- Food technology and CPG
- Enterprise SaaS with AI features
- Research and applied AI labs

---

### Slide 5 — Wrap-Up

**Goal:** Give a hiring manager or recruiter every link they need in one place, plus any additional credentials.

Suggested content:

**Live project:**
- 🌐 EverFlavor Kitchen: [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/)

**Code and portfolio:**
- 💻 Capstone repo: [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI)
- 📁 AI Portfolio: [github.com/Chloe-Tu2/Applied-AI-Portfolio-Chloe-Tu](https://github.com/Chloe-Tu2/Applied-AI-Portfolio-Chloe-Tu)

**Contact:**
- *(Add your preferred contact email or LinkedIn URL here)*

**Program:**
- Applied AI & Robotics, Houston Community College
- ITAI 2277 — Artificial Intelligence Resources & References
- Professor: Anna Devarakonda
- Team EverGlow: Chloe Tu, Eva Abou Abou Harb, Francisco Medina

**Additional skills and certifications:**
- *(List any relevant certifications: Google, AWS, Coursera, etc.)*
- *(List any other programming languages, frameworks, or tools)*

---

## Submission Checklist

- [ ] PDF named exactly `Pf_ChloeTu_ITAI_2277.pdf`
- [ ] Submitted to LMS (Canvas / course portal) by December 5, 2026 at 11:59 PM
- [ ] GitHub repository link included in the PDF or submission notes
- [ ] Repository is public and accessible to anyone with the link
- [ ] All five slides present in the PDF
- [ ] Copy of PDF placed in this folder for portfolio completeness

---

## Note on the PDF

The `Pf_ChloeTu_ITAI_2277.pdf` file is the **official course submission**. This README documents its content so the portfolio is readable without downloading the PDF. The PDF and this README should be consistent — if you update the presentation, update this document too.

---

[← Back to course folder](../README.md) | [Phase 05 — Final Package](../Phase-05-Final-Presentation-and-Completed-Project-Package/)
