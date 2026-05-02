# Project 06 — Analyzing *Arrival* Through the Lens of NLP

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![NLP](https://img.shields.io/badge/topic-Natural_Language_Processing-9cf.svg)
![BERT](https://img.shields.io/badge/model-BERT-yellow.svg)
![Transformers](https://img.shields.io/badge/framework-Hugging_Face_Transformers-orange.svg)
![Google Colab](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![Creative AI](https://img.shields.io/badge/type-Creative_AI_Application-ff69b4.svg)
![Semantic Similarity](https://img.shields.io/badge/technique-Semantic_Similarity-blueviolet.svg)
![Attention Visualization](https://img.shields.io/badge/technique-Attention_Visualization-green.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Project Heptapod — Start](./Results-%26-Visualizations/start_project_Heptapod.png)

**Project Heptapod** applies the full toolkit of Natural Language Processing to analyze the film *Arrival* (2016, dir. Denis Villeneuve) — a science fiction masterpiece about language, time, and communication across species. The film's central thesis is drawn from the **Sapir-Whorf hypothesis**: that the language you speak shapes how you think, and that a language without linear time would produce a consciousness that perceives all of time simultaneously.

This project uses NLP methods — BERT embeddings, self-attention visualization, cosine similarity analysis, and a custom logogram generator — to explore that hypothesis computationally. It is simultaneously a technical NLP project and a creative humanistic investigation: using AI tools to decode a fictional alien language and model what it means for language to shape cognition.

---

## Problem Statement

*Arrival*'s central thesis is that **language shapes thought** — and that a language without linear time would produce a consciousness that perceives all time simultaneously. The Heptapods write in circular logograms with no beginning and no end; their language encodes the entire meaning of a statement radially rather than sequentially.

This project asks: **Can NLP tools like BERT embeddings and attention visualization reveal how circular, time-invariant language structure differs from linear human language — and can we simulate what Heptapod B might look like computationally?**

---

## Approach and Methodology

### NLP Analysis Pipeline

**1. Self-Attention Visualization (BERT)**
- Loaded `bert-base-uncased` from Hugging Face Transformers.
- Extracted multi-head attention weight matrices from BERT's 12 attention heads.
- Visualized how meaning flows between tokens in a sentence — revealing which words BERT attends to when processing each word.
- Compared attention patterns in linear vs. circular sentence structures to test whether BERT's bidirectional attention approximates non-linear language processing.

**2. Temporal Concept Similarity (BERT Embeddings)**
- Computed contextualized embeddings for temporal concepts: *past*, *present*, *future*, *simultaneous*, *eternal*, *now*, *always*.
- Used cosine similarity to map how these concepts cluster in BERT's 768-dimensional embedding space.
- Finding: BERT's embedding space reflects human linear time perception — *past/present/future* cluster closely, while *simultaneous/eternal* are outliers.

**3. Heptapod Logogram Generator**
- Built a custom Python generator that creates circular, non-linear "logograms" — the written form of Heptapod B.
- Generated symbols encode meaning radially rather than sequentially, using matplotlib's polar coordinate system.
- Each logogram is procedurally generated from semantic content, demonstrating that circular encoding of meaning is computationally representable.

**4. NLP Paradigm Comparison**
- Compared classical (bag-of-words), sequential (RNN), and attention-based (Transformer) NLP paradigms.
- Mapped each to the way *Arrival*'s human linguists approach decoding alien communication — from word-frequency counting to sequential parsing to holistic attention.

---

## Results & Visualizations

| **Project Heptapod Logo**  | **Self-Attention Heatmap - BERT**  | **Attention Map — Bird** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|![Project Heptapod Logo](./Results-%26-Visualizations/Project_Heptapod_logo.png)| ![Project Heptapod Logo](./Results-%26-Visualizations/Project_Heptapod_logo.png) | ![Attention Map for Bird](./Results-%26-Visualizations/Attention_map_for_bird.png) |



![Project Heptapod Logo](./Results-%26-Visualizations/Project_Heptapod_logo.png)

![Self-Attention Heatmap — BERT](./Results-%26-Visualizations/Self-Attention_Heatmap.png)

![Circular Attention Visualization](./Results-%26-Visualizations/Circular_Attention_Visualization.png)

![Linear vs. Circular Language Visualization](./Results-%26-Visualizations/Linear_vs_Circular_Language_Visualization.png)

![Temporal Concepts Similarity in BERT](./Results-%26-Visualizations/Temporal_Concepts_Similarity_In_BERT.png)

![Heptapod Logogram Generator](./Results-%26-Visualizations/Heptapod_Logogram_Generator.png)

![Louise's Whiteboard](./Results-%26-Visualizations/Louise's_Whiteboard.png)

![Operation First Contact](./Results-%26-Visualizations/Operation_First_Contact.png)

![End of Transmission](./Results-%26-Visualizations/End_of_Transmission.png)

**Key Findings:**

| Finding | Technical Detail |
|---|---|
| BERT models bidirectional context | 12 attention heads simultaneously attend backward and forward — closer to circular than RNN's sequential processing |
| Temporal concepts cluster linearly | *past/present/future* form a tight cluster in BERT space; *simultaneous/eternal* are semantic outliers |
| Circular logogram generation works | Radial, polar-coordinate encoding successfully represents meaning without sequential order |
| The gap remains significant | Current NLP cannot model non-linear time perception — but multi-head attention is the closest computational approximation |

---

## Learning Outcomes

- Gained deep understanding of **BERT's architecture**: bidirectional transformers, masked language modeling (MLM), next-sentence prediction (NSP), and the 12-head attention mechanism.
- Learned to extract and visualize **attention weights** as an interpretability tool — seeing which tokens a model focuses on when making predictions.
- Applied **semantic similarity** analysis using cosine distance on contextualized BERT embeddings — understanding that similar words are close in the high-dimensional embedding space.
- Connected NLP theory to **humanistic inquiry** — demonstrating AI's capacity for creative and analytical cross-disciplinary work.
- Understood the Sapir-Whorf hypothesis computationally: BERT's embedding geometry reflects the linear temporal structure of English, not the circular structure of Heptapod B.
- Developed a creative AI application — the Heptapod logogram generator — that demonstrates generative NLP applied to a fictional linguistic framework.

---

## Project Structure

```text
Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP/
├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb                             # Full Colab notebook (source)
├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb-Colab.pdf                   # Full Colab notebook (PDF export)
├── P06_Analyzing-Arrival-Through-the-Lens-of-NLP.pdf          # Project report & analysis write-up
├── Results-&-Visualizations/                                  # All generated visualizations
│   ├── start_project_Heptapod.png                             # Project intro visualization
│   ├── Project_Heptapod_logo.png                              # Project Heptapod logo
│   ├── NLP_Paradigm_Comparison.png                            # NLP paradigm overview chart
│   ├── Self-Attention_Heatmap.png                             # BERT self-attention heatmap
│   ├── Circular_Attention_Visualization.png                   # Circular attention map
│   ├── Linear_vs_Circular_Language_Visualization.png          # Linear vs circular language
│   ├── Temporal_Concepts_Similarity_In_BERT.png               # Temporal concepts in BERT space
│   ├── Heptapod_Logogram_Generator.png                        # Generated alien logograms
│   ├── Louise's_Whiteboard.png                                # Film whiteboard reference
│   ├── Operation_First_Contact.png                            # Operation visualization
│   └── End_of_Transmission.png                                # Final transmission visual
└── README.md
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

This project uses **no external training datasets**. The NLP analysis is performed on manually curated sentences.

**BERT model** (automatically downloaded from Hugging Face Hub on first run, ~440MB):
```python
from transformers import BertModel, BertTokenizer
tokenizer = BertTokenizer.from_pretrained('bert-base-uncased')
model = BertModel.from_pretrained('bert-base-uncased')
```

*Film reference: Arrival (2016), dir. Denis Villeneuve. Based on "Story of Your Life" by Ted Chiang.*
