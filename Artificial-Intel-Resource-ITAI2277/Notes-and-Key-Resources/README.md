# Notes and Key Resources

> **ITAI 2277 · Houston Community College · Applied AI & Robotics**
> **Student:** Chloe Tu · **Term:** Fall 2026

A curated reference list of every tool, framework, dataset, and documentation source actually used in building EverFlavor AI across Phases 01–04. Written for a stranger — no assumed context.

---

## Why This List Exists

Applied AI projects draw from dozens of libraries, APIs, and datasets. This folder documents exactly what was used, why, and where to find it. It is not a comprehensive survey of AI tools; it is a precise record of what this specific project needed.

---

## Agent Orchestration

### CrewAI
- **What it is:** A Python framework for building multi-agent AI systems where agents have defined roles, backstories, and tool access, and are coordinated by a planner.
- **How it was used:** Orchestrates the three EverFlavor agents (Nutritionist & Preference, Chef, Sourcing). The CrewAI planner decides which agent runs and in what order based on the user's request.
- **Link:** [github.com/joaomdmoura/crewAI](https://github.com/joaomdmoura/crewAI)
- **Docs:** [docs.crewai.com](https://docs.crewai.com)
- **Phase used:** 03, 04

### Ollama
- **What it is:** A tool for running large language models locally on your own machine. No API key required; runs fully offline.
- **How it was used:** Serves the local LLM that the CrewAI agents use for reasoning and tool-calling. Used in Phase 03 for the 33 × 2 agent evaluation tests, and in Phase 04 for the live app backend.
- **Link:** [ollama.ai](https://ollama.ai)
- **Phase used:** 03, 04

---

## Frontend / Deployment

### Streamlit
- **What it is:** A Python library for building interactive web applications with minimal frontend code. No HTML or JavaScript required for most features.
- **How it was used:** The entire EverFlavor Kitchen UI — 7 kitchen pages, waiter chat, Houston map, cookbook, profile — is built in Streamlit and deployed on Streamlit Community Cloud (free tier).
- **Link:** [streamlit.io](https://streamlit.io)
- **Community Cloud (free hosting):** [streamlit.io/cloud](https://streamlit.io/cloud)
- **Phase used:** 04 (Gradio was originally planned in Phase 01 but replaced)

---

## Machine Learning / Training

### scikit-learn
- **What it is:** The standard Python library for classical ML — classifiers, regressors, preprocessing, pipelines, evaluation metrics.
- **How it was used:** Cuisine classifier (TF-IDF + classifier, val acc 0.77), nutrition estimator (regression, ~102 kcal typical error), origin model (37-country classifier, 89.3% on high-confidence slice).
- **Link:** [scikit-learn.org](https://scikit-learn.org)
- **Phase used:** 03

### PyTorch
- **What it is:** A deep learning framework for training neural networks. Used here for the computer vision freshness model.
- **How it was used:** Freshness CV model — fine-tuned CNN on ~45,000 food photographs. Test accuracy: 98.8% produce, 87.4% fish (after retraining; initial fish macro F1 was 0.60, improved to 0.87).
- **Link:** [pytorch.org](https://pytorch.org)
- **Phase used:** 03

### Hugging Face Transformers
- **What it is:** Library providing pretrained model weights, tokenizers, and training utilities for NLP and CV models.
- **How it was used:** Tokenizers for the origin model; dataset loading utilities.
- **Link:** [huggingface.co/docs/transformers](https://huggingface.co/docs/transformers)
- **Phase used:** 03

---

## Data Sources

### USDA FoodData Central
- **What it is:** The U.S. Department of Agriculture's official nutritional database — per-ingredient calorie, protein, fat, carbohydrate, fiber data.
- **How it was used:** Ground-truth nutrition per ingredient for the nutrition estimator training data and the app's calorie calculator.
- **Access:** Free API key at [fdc.nal.usda.gov](https://fdc.nal.usda.gov/). A local snapshot of the database was downloaded for pipeline speed.
- **Note:** The pipeline initially had bad USDA matches (e.g., "tomato paste" matching to "almond paste"). The top 200 ingredients were hand-corrected in Phase 03.
- **Phase used:** 02, 03, 04

### Open Food Facts
- **What it is:** A crowd-sourced, open-license (CC BY-SA) database of packaged food products with nutrition information.
- **How it was used:** Supplementary nutrition data for packaged and processed ingredients not well-represented in USDA.
- **Access:** [world.openfoodfacts.org](https://world.openfoodfacts.org/) — no authentication required.
- **Phase used:** 02

### Food.com Dataset (Kaggle)
- **What it is:** A large dataset of recipes and user interactions from Food.com, available on Kaggle. Contains recipe text, ingredient lists, and user ratings.
- **How it was used:** Primary recipe corpus for the cuisine classifier and origin model. 63,903 recipes used for cuisine classifier training.
- **Access:** [kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions) — free Kaggle account required.
- **Phase used:** 02, 03

### Hugging Face — recipes-with-nutrition
- **What it is:** A Hugging Face dataset of recipes pre-paired with nutrition estimates.
- **How it was used:** Additional training data for the nutrition estimator (171,919 total training rows).
- **Access:** `datasets.load_dataset("Shengtao/recipe")` — no authentication.
- **Link:** [huggingface.co/datasets/Shengtao/recipe](https://huggingface.co/datasets/Shengtao/recipe)
- **Phase used:** 02, 03

### CulinaryDB
- **What it is:** A research database of recipes annotated with cuisine labels, from IIIT Delhi.
- **How it was used:** Cuisine-annotated recipes to supplement Food.com for underrepresented cuisine families.
- **Access:** [cosylab.iiitd.edu.in/culinarydb](https://cosylab.iiitd.edu.in/culinarydb/) — research use.
- **Phase used:** 02, 03

### RecipeDB (Considered, Not Used)
- **What it is:** Another research recipe database from IIIT Delhi.
- **Why not used:** Coverage and license terms were not adequate for the feature set needed at the scale required.
- **Phase used:** Evaluated in Phase 02, not used.

---

## Geolocation

### Google Places API
- **What it is:** Google's API for finding businesses, addresses, and places by type and location.
- **How it was used:** Finding specialty grocery stores (Asian, Middle Eastern, Latin American, African, European) within a user-specified driving radius in Houston.
- **Access:** Requires a Google Cloud API key. [developers.google.com/maps/documentation/places](https://developers.google.com/maps/documentation/places)
- **Note:** Rate-limited in the pipeline to stay within free-tier quotas.
- **Phase used:** 01 (planned), 02, 04

### OpenStreetMap
- **What it is:** A free, open geographic database of the world.
- **How it was used:** Supplementary map data for the Houston map feature.
- **Link:** [openstreetmap.org](https://www.openstreetmap.org)
- **Phase used:** 04

---

## Knowledge Base

### Wikipedia / Wikidata
- **What it is:** Wikipedia is the free encyclopedia; Wikidata is the structured knowledge graph behind it. Both are publicly accessible via API.
- **How it was used:** Source of the 4,885 dish entries in the waiter knowledge base. Walter and Nathalie (waiter agents) draw facts only from this sourced knowledge — they never generate answers outside it.
- **API:** [en.wikipedia.org/api/rest_v1](https://en.wikipedia.org/api/rest_v1) · [wikidata.org/wiki/Special:EntityData](https://www.wikidata.org/wiki/Special:EntityData)
- **Phase used:** 04

---

## Ethics and Licensing

### Documentation Created for This Project
- `docs/sources.md` — full provenance for every dataset used
- `docs/data_dictionary.md` — field definitions for processed datasets
- `docs/ethics_privacy.md` — ethics and privacy framework

### Key Commitments
- **Public/open data only** — no scraping behind authentication walls
- **API rate limits respected** — USDA and Places calls are rate-limited in code
- **No PII** — no user data stored server-side
- **License compliance** — Food.com used under Kaggle ToS; Open Food Facts under CC BY-SA; attribution in `docs/sources.md`
- **Session-only user profile** — cleared when the browser session ends

### License References
- [Creative Commons CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/) — Open Food Facts, Wikipedia content
- [Kaggle Terms of Service](https://www.kaggle.com/terms) — Food.com dataset
- [MIT License](https://opensource.org/licenses/MIT) — EverFlavor AI codebase

---

## Dev Tools

| Tool | Use |
|------|-----|
| [Jupyter](https://jupyter.org) | EDA, cleaning, and training notebooks |
| [pytest](https://pytest.org) | 314 test functions across 37 files; 579 passed on clean run |
| [Git / GitHub](https://github.com) | Version control and public portfolio hosting |
| [pandas](https://pandas.pydata.org) | Data manipulation throughout all phases |
| [numpy](https://numpy.org) | Numerical operations in training pipelines |
| [matplotlib](https://matplotlib.org) / [seaborn](https://seaborn.pydata.org) | EDA visualizations |

---

[← Back to course folder](../README.md)
