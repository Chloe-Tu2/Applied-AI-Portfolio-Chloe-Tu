# ITAI 2277 — Artificial Intelligence Resources & References

> **Houston Community College · Applied AI & Robotics Program**
> **Student:** Chloe Tu · **Professor:** Anna Devarakonda · **Term:** Fall 2026

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Live_App-FF4B4B?logo=streamlit)](https://everflavor-ai-kitchen.streamlit.app/)
[![CrewAI](https://img.shields.io/badge/CrewAI-Multi--Agent-6C63FF)](https://github.com/joaomdmoura/crewAI)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn)](https://scikit-learn.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-CV-EE4C2C?logo=pytorch)](https://pytorch.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas)](https://pandas.pydata.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter)](https://jupyter.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Course Overview

**ITAI 2277** is a capstone-track course in the Houston Community College Applied AI & Robotics program. It moves students from idea to deployed system across five structured phases: proposal, data pipeline, model training, integrated prototype, and professional portfolio packaging.

This folder is the course deliverable inside the larger Applied AI portfolio. Every subfolder is self-contained — a stranger with no context from the class can read the README and understand what was built, why, and what was learned. The portfolio is built to serve as **hiring evidence**, not an archive of raw submissions.

💻 **EverFlavor GitHub:** [The-EverFlavor-AI-Chloe-Tu](https://github.com/Chloe-Tu2/The-EverFlavor-AI)
📁 **Parent portfolio:** [Applied-AI-Portfolio-Chloe-Tu](https://github.com/Chloe-Tu2/Applied-AI-Portfolio-Chloe-Tu)

---

## Featured Capstone Project

**EverFlavor AI** is a live, multi-agent culinary assistant that recommends authentic global recipes matched to a user's remaining calorie budget, dietary restrictions, and local ingredient availability. It was built by **Team EverGlow** (Chloe Tu, Eva Abou Abou Harb, Francisco Medina) across the full semester.

| Attribute | Detail |
|-----------|--------|
| **System type** | Conversational multi-agent (CrewAI) |
| **Agents** | Nutritionist & Preference · Chef · Sourcing |
| **Cuisine families** | Asian · European · Latin American · African · Middle Eastern |
| **Live app** | [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/) |
| **Code repository** | [github.com/Chloe-Tu2/The-EverFlavor-AI](https://github.com/Chloe-Tu2/The-EverFlavor-AI) |
| **Test suite** | 579 passed · 26 skipped · 0 failed (Nov 14, 2026) |
| **Safety approach** | Hard-coded gate — the LLM never decides safety |
| **Privacy** | No server-side user database; cookbook is browser-only |
| **Phase folders** | [Phase-04 (MVP)](./Phase-04-Integrated-System-Prototype-MVP/) · [Phase-05 (Presentation)](./Phase-05-Final-Presentation-and-Completed-Project-Package/) |

---

## Project Directory

| Folder | Phase | Description |
|--------|-------|-------------|
| [Phase-01-Capstone-Proposal-and-Problem-Framing](./Phase-01-Capstone-Proposal-and-Problem-Framing/) | 01 · Week 3 | Problem definition, user personas, three-agent architecture, planned tech stack |
| [Phase-02-Data-Pipeline-and-Exploratory-Analysis](./Phase-02-Data-Pipeline-and-Exploratory-Analysis/) | 02 · Weeks 4–6 | Six data sources, cleaning pipeline, feature engineering, ethics documentation |
| [Phase-03-Trained-Models-and-Evaluation](./Phase-03-Trained-Models-and-Evaluation/) | 03 · Weeks 7–10 | Four trained ML models, local LLM agent integration, safety gate evaluation |
| [Phase-04-Integrated-System-Prototype-MVP](./Phase-04-Integrated-System-Prototype-MVP/) | 04 · Weeks 11–13 | Live Streamlit MVP, 579-test suite, 200+ red-team safety checks, Houston map |
| [Phase-05-Final-Presentation-and-Completed-Project-Package](./Phase-05-Final-Presentation-and-Completed-Project-Package/) | 05 · Final | Employer-facing 5-slide PDF, portfolio packaging, public checklist |
| [Capstone-EverFlavor-AI](./Capstone-EverFlavor-AI/) | Full arc | End-to-end capstone summary — start here for the full product story |
| [Notes-and-Key-Resources](./Notes-and-Key-Resources/) | Reference | Curated links and notes for every tool, dataset, and framework actually used |
| [Presentation](./Presentation/) | Final | 5-slide content outline for `Pf_ChloeTu_ITAI_2277.pdf` |

---

## Notebooks / Technical Artifacts Overview

| Artifact | Phase | Purpose |
|----------|-------|---------|
| Cuisine classifier notebook | 03 | Train/evaluate 5-family classifier (val acc 0.77, macro F1 0.62) |
| Nutrition estimator notebook | 03 | Regression model, typical error ~102 kcal |
| Origin model notebook | 03 | 37-country classifier, 89.3% on high-confidence slice |
| Freshness CV notebook | 03 | Computer-vision model, 98.8% produce / 87.4% fish accuracy |
| Data cleaning & EDA notebooks | 02 | Pipeline from six raw sources to processed features |
| Agent integration notebook | 04 | CrewAI planner + tool-calling LLM assembly |
| Red-team safety notebook | 04 | 200+ adversarial prompts, 0 LLM-decided safety outcomes |

---

## Key Learning Outcomes

- **Multi-agent system design:** Decomposed a complex user request into three cooperating agents with well-defined roles and tool interfaces.
- **Data quality over data quantity:** Cleaning six heterogeneous sources was harder and more impactful than any model choice.
- **Safety-by-code:** Learned why dietary safety constraints must live in deterministic code, not LLM reasoning — the LLM cannot override the gate.
- **Evaluation discipline:** Each model has a held-out test set, explicit failure analysis, and an honest account of what did not improve results.
- **End-to-end deployment:** Shipped a live Streamlit app on Community Cloud with a 314-function test suite.
- **Portfolio communication:** Turning six months of technical work into two-minute hiring evidence is itself a skill.

---

## Tools & Frameworks

| Category | Tools |
|----------|-------|
| **Agent orchestration** | CrewAI, Ollama (local LLM) |
| **Frontend / deployment** | Streamlit, Streamlit Community Cloud |
| **ML / training** | scikit-learn, PyTorch, Hugging Face Transformers |
| **Data** | pandas, USDA FoodData Central, Open Food Facts, Food.com (Kaggle), HuggingFace recipes-with-nutrition, CulinaryDB |
| **Computer vision** | PyTorch (freshness model) |
| **Geolocation** | Google Places API, OpenStreetMap |
| **Knowledge base** | Wikipedia / Wikidata (4,885 dish entries) |
| **Dev tools** | Jupyter, pytest, Git, GitHub |

---

## Real-World Applications

The skills and system architecture from this course apply directly to production AI problems:

- **Dietary compliance tools** for hospital nutrition departments, fitness platforms, and corporate wellness programs.
- **Multi-agent RAG systems** for any domain requiring tool-calling agents with hard safety constraints (legal, medical, finance).
- **Computer vision for food quality** in supply-chain freshness inspection or restaurant inventory.
- **Hyperlocal recommendation engines** that combine LLM reasoning with real geographic and inventory data.
- **Privacy-preserving AI** — the EverFlavor approach (no server-side user DB, session-only profile) is a reusable pattern for GDPR/CCPA-sensitive applications.

---

## Repository Structure

```
Artificial-Intel-Resource-ITAI2277/
├── README.md                                          ← You are here
├── Phase-01-Capstone-Proposal-and-Problem-Framing/
│   ├── README.md
│   ├── Phase_01_EverGlow_ITAI_2277.pdf
│   └── Capstone-Project-Proposal_Slides_EverGlow_ITAI_2277.pdf
├── Phase-02-Data-Pipeline-and-Exploratory-Analysis/
│   ├── README.md
│   └── Phase_02_EverGlow_ITAI_2277.pdf
├── Phase-03-Trained-Models-and-Evaluation/
│   ├── README.md
│   └── Phase_03_EverGlow_ITAI_2277.pdf
├── Phase-04-Integrated-System-Prototype-MVP/
│   ├── README.md
│   └── Phase_04_EverGlow_ITAI_2277.pdf
├── Phase-05-Final-Presentation-and-Completed-Project-Package/
│   ├── README.md
│   └── Pf_ChloeTu_ITAI_2277.pdf
├── Capstone-EverFlavor-AI/
│   └── README.md
├── Notes-and-Key-Resources/
│   └── README.md
└── Presentation/
    └── README.md
```

---

## How to Navigate

**Recruiter / hiring manager — suggested 10-minute path:**

1. **[Capstone-EverFlavor-AI](./Capstone-EverFlavor-AI/)** — Full product summary and live app link. Open [everflavor-ai-kitchen.streamlit.app](https://everflavor-ai-kitchen.streamlit.app/) in your browser.
2. **[Phase-04 — Integrated System Prototype / MVP](./Phase-04-Integrated-System-Prototype-MVP/)** — What was actually shipped: 579-test suite, Houston map, pixel chefs, waiter agents with sourced knowledge.
3. **[Phase-03 — Trained Models & Evaluation](./Phase-03-Trained-Models-and-Evaluation/)** — Four trained models with concrete metrics, honest failure analysis, and the safety architecture.
4. **[Phase-02 — Data Pipeline & EDA](./Phase-02-Data-Pipeline-and-Exploratory-Analysis/)** — Six data sources, cleaning decisions, feature engineering.
5. **[Phase-01 — Capstone Proposal](./Phase-01-Capstone-Proposal-and-Problem-Framing/)** — Original idea framing, personas, architecture design.
6. **[Phase-05 — Presentation PDF](./Phase-05-Final-Presentation-and-Completed-Project-Package/)** — `Pf_ChloeTu_ITAI_2277.pdf` employer-facing 5-slide summary.

---

## Links

| Resource | URL |
|----------|-----|
| 🍜 Live EverFlavor App | https://everflavor-ai-kitchen.streamlit.app/ |
| 💻 EverFlavor GitHub | https://github.com/Chloe-Tu2/The-EverFlavor-AI |
| 📁 Main AI Portfolio | https://github.com/Chloe-Tu2/Applied-AI-Portfolio-Chloe-Tu |
