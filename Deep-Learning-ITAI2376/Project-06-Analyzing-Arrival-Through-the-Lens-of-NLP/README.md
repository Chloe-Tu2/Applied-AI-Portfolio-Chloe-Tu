# Project 06 — Analyzing *Arrival* Through the Lens of NLP

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![NLP](https://img.shields.io/badge/topic-Natural_Language_Processing-9cf.svg)
![BERT](https://img.shields.io/badge/model-BERT-yellow.svg)
![Transformers](https://img.shields.io/badge/framework-Hugging_Face_Transformers-orange.svg)
![Jupyter](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![Creative AI](https://img.shields.io/badge/type-Creative_AI_Application-ff69b4.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Project Heptapod — Start](./Results-%26-Visualizations/start_project_Heptapod.png)

**Project Heptapod** applies the full toolkit of Natural Language Processing to analyze the film *Arrival* (2016) — a science fiction masterpiece about language, time, and communication across species. The project uses NLP methods including BERT embeddings, self-attention visualization, and semantic similarity analysis to explore how the film's alien language (Heptapod B) embeds non-linear time perception into its grammar.

This is both a technical NLP project and a creative humanistic one: using AI tools to decode a fictional alien language and investigate what it means for language to shape cognition.

---

## Problem Statement

*Arrival*'s central thesis, drawn from the Sapir-Whorf hypothesis, is that **language shapes thought** — and that a language without linear time would produce a consciousness that perceives all time simultaneously. This project asks: **Can NLP tools like BERT embeddings and attention visualization reveal how circular, time-invariant language structure differs from linear human language — and can we simulate what Heptapod B might look like computationally?**

---

## Approach and Methodology

### NLP Analysis Pipeline

**1. Self-Attention Visualization (BERT)**
- Used BERT's multi-head attention weights to visualize how meaning flows between tokens.
- Compared attention patterns in linear vs. circular sentence structures.

**2. Temporal Concept Similarity (BERT Embeddings)**
- Computed semantic similarity between temporal concepts: *past*, *present*, *future*, *simultaneous*, *eternal*.
- Mapped how these concepts cluster in BERT's embedding space.

**3. Heptapod Logogram Generator**
- Built a custom generator that creates circular, non-linear "logograms" — the written form of Heptapod B.
- Generated symbols encode meaning radially rather than sequentially.

**4. NLP Paradigm Comparison**
- Compared classical (bag-of-words), sequential (RNN), and attention-based (Transformer) NLP paradigms.
- Mapped each to the way *Arrival*'s human linguists approach decoding alien communication.

---

## Results and Evaluation

![Project Heptapod Logo](./Results-%26-Visualizations/Project_Heptapod_logo.png)

![NLP Paradigm Comparison](./Results-%26-Visualizations/NLP_Paradigm_Comparison.png)

![Self-Attention Heatmap — BERT](./Results-%26-Visualizations/Self-Attention_Heatmap.png)

![Circular Attention Visualization](./Results-%26-Visualizations/Circular_Attention_Visualization.png)

![Linear vs. Circular Language Visualization](./Results-%26-Visualizations/Linear_vs_Circular_Language_Visualization.png)

![Temporal Concepts Similarity in BERT](./Results-%26-Visualizations/Temporal_Concepts_Similarity_In_BERT.png)

![Heptapod Logogram Generator](./Results-%26-Visualizations/Heptapod_Logogram_Generator.png)

![Louise's Whiteboard](./Results-%26-Visualizations/Louise's_Whiteboard.png)

![Operation First Contact](./Results-%26-Visualizations/Operation_First_Contact.png)

![End of Transmission](./Results-%26-Visualizations/End_of_Transmission.png)

**Key Findings:**
- BERT's self-attention naturally models bidirectional context — a step toward circular, non-sequential language processing.
- Temporal concepts cluster in BERT's embedding space in ways that reflect human linear time perception.
- The Heptapod logogram generator demonstrates that circular, radial encoding of meaning is computationally representable.
- The gap between current NLP and true non-linear cognition remains significant — but attention mechanisms are the closest approximation.

---

## Learning Outcomes

- Gained deep understanding of **BERT's architecture** — bidirectional transformers, masked language modeling, and attention heads.
- Learned to extract and visualize **attention weights** as interpretability tools.
- Applied **semantic similarity** analysis using cosine distance on BERT embeddings.
- Connected NLP theory to **humanistic inquiry** — demonstrating AI's capacity for creative and analytical cross-disciplinary work.
- Understood the Sapir-Whorf hypothesis computationally: how language structure shapes the representational space of meaning.

---

## Project Structure

```text
Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP/
├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb-Colab.pdf                   # Full Colab notebook (PDF export)
├── P06_Analyzing-Arrival-Through-the-Lens-of-NLP.pdf          # Project report & analysis write-up
├── Results-&-Visualizations/                                  # All generated visualizations
│   ├── start_project_Heptapod.png                             # Project intro visualization
│   ├── Project_Heptapod_logo.png                              # Project Heptapod logo
│   ├── NLP_Paradigm_Comparison.png                            # NLP paradigm overview chart
│   ├── Self-Attention_Heatmap.png                             # BERT self-attention visualization
│   ├── Circular_Attention_Visualization.png                   # Circular attention map
│   ├── Linear_vs_Circular_Language_Visualization.png          # Linear vs circular language
│   ├── Temporal_Concepts_Similarity_In_BERT.png               # Temporal similarity in BERT space
│   ├── Heptapod_Logogram_Generator.png                        # Generated alien logograms
│   ├── Louise's_Whiteboard.png                                # Whiteboard reference image
│   ├── Operation_First_Contact.png                            # Operation visual
│   └── End_of_Transmission.png                                # Final transmission visual
└── README.md                                                  # Project documentation (this file)
```

---

## Dependencies / Requirements

```bash
pip install transformers torch numpy matplotlib scikit-learn seaborn jupyter
```

**Python:** 3.8+

```
transformers >= 4.20
torch >= 1.12
numpy >= 1.21
matplotlib >= 3.5
scikit-learn >= 1.0
seaborn >= 0.11
jupyter / Google Colab
```

---

## Running the Notebook

**Recommended: Google Colab (GPU)**
1. Open [colab.research.google.com](https://colab.research.google.com)
2. Upload `P06_ARRIVAL_HEPTAPOD_LAB.ipynb`
3. Runtime → Change runtime type → T4 GPU
4. Run All Cells

```bash
# Or locally:
pip install transformers torch
jupyter notebook P06_ARRIVAL_HEPTAPOD_LAB.ipynb
```

---

## Data Access

This project uses **no external training datasets**. The NLP analysis is performed on:

- **Text input:** Manually curated sentences representing linear and circular language structures.
- **BERT model:** Automatically downloaded from Hugging Face Hub on first run:
  ```python
  from transformers import BertModel, BertTokenizer
  tokenizer = BertTokenizer.from_pretrained('bert-base-uncased')
  model = BertModel.from_pretrained('bert-base-uncased')
  ```
- **Model size:** ~440MB (downloaded automatically from Hugging Face).

*Film reference: Arrival (2016), dir. Denis Villeneuve. Based on "Story of Your Life" by Ted Chiang.*
