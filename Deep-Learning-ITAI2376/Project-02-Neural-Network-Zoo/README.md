# Project 02 — Neural Network Zoo

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Deep Learning](https://img.shields.io/badge/topic-Deep_Learning-blueviolet.svg)
![Neural Networks](https://img.shields.io/badge/topic-Neural_Network_Architectures-orange.svg)
![Visual Showcase](https://img.shields.io/badge/type-Visual_Showcase-lightgrey.svg)
![PowerPoint](https://img.shields.io/badge/tool-PowerPoint-B7472A.svg)
![Web App](https://img.shields.io/badge/tool-Interactive_Web_App-success.svg)
![Mantis Shrimp](https://img.shields.io/badge/theme-Mantis_Shrimp-9cf.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

### ConvoShrimp - CNN Neural Network Lookbook

<img src="./Results-%26-Visualizations/09.png" alt="ConvoShrimp" width="85%"/>

**[▶ ConvoShrimp - CNN Neural Network Lookbook Quick Access — ](https://convoshrimp.netlify.app/)**  

* This an video clip The Mantis Shrimp as a Model for Convolutional Neural Networks **Note: AI video by Google Gemini Veo 3** *

**[▶ Quick Access — Watch the Full Clip Video on Google Drive](https://drive.google.com/file/d/1Lm6TBF2v0JirmmkC63ERDOhTKxgsqHc_/view)**  
*See the download MP4 version — [full cilp video below](#demo-video) 


</div>

---

## Project Overview

This project is a visual and conceptual exploration of the **Neural Network Zoo** — the full landscape of deep learning architectures that have shaped modern AI. Rather than focusing on a single model, the project maps the entire evolutionary tree of neural networks: from the original Perceptron and MLP through CNNs, RNNs, LSTMs, and Transformers, all the way to Generative Models, Graph Neural Networks, and emerging architectures like Mamba.

The centerpiece is a custom-designed **3D rotating architectural showcase** themed around the **Mantis Shrimp** — an animal with 16 types of photoreceptors, chosen as a metaphor for how different neural architectures "see" data in fundamentally different ways. Just as the mantis shrimp processes light across 16 spectral channels simultaneously, modern neural architectures process data through multiple parallel representations and inductive biases.

The project also includes the **[ConvoShrimp](./Convoshrimp)** interactive web application — a fully browsable, live interface for exploring the neural network zoo.

---

## Problem Statement

Deep learning practitioners often develop tunnel vision — mastering one or two architectures while remaining unaware of the broader architectural landscape. This creates missed opportunities: applying a CNN where a GNN would excel, using an MLP where sequence models are needed, or missing that a diffusion model is better suited than a GAN. This project asks: **What is the full map of neural network architectures, what problem domain is each one designed to solve, and how did each innovation build on and correct the failures of its predecessor?**

---

## Approach and Methodology

### Architecture Survey
Catalogued and categorized **30+ neural network types**, organized by computational paradigm. For each architecture, documented:
- Core innovation that motivated its creation
- Inductive bias and optimal problem domain
- Known limitations and what architecture superseded it
- Landmark paper and year of introduction

### Visual Design
Created a polished PowerPoint presentation using custom graphics, a Mantis Shrimp visual theme, and hierarchical visual taxonomy. Each architecture family received a dedicated slide with diagram, use-case, and comparison to adjacent architectures.

### 3D Video Showcase
Produced a rotational 3D visualization video (`P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4`) animating through the architecture zoo.

### ConvoShrimp Sub-Project
The [`Convoshrimp/`](./Convoshrimp) interactive web application brings the neural network zoo to life as a browsable, interactive interface.

---

## Results & Visualizations

### Architecture Showcase Gallery

![Neural Network Zoo — Slide 01](./Results-%26-Visualizations/01.png)

![Neural Network Zoo — Slide 02](./Results-%26-Visualizations/02.png)

![Neural Network Zoo — Slide 03](./Results-%26-Visualizations/03.png)

![Neural Network Zoo — Slide 04](./Results-%26-Visualizations/04.png)

![Neural Network Zoo — Slide 05](./Results-%26-Visualizations/05.png)

![Neural Network Zoo — Slide 06](./Results-%26-Visualizations/06.png)

![Neural Network Zoo — Slide 07](./Results-%26-Visualizations/07.png)

![Neural Network Zoo — Slide 08](./Results-%26-Visualizations/08.png)

![Neural Network Zoo — Slide 09](./Results-%26-Visualizations/09.png)

![Neural Network Zoo — Slide 10](./Results-%26-Visualizations/10.jpeg)

![Neural Network Zoo — Slide 11](./Results-%26-Visualizations/11.png)

![Neural Network Zoo — Slide 12](./Results-%26-Visualizations/12.png)

---

## Architecture Taxonomy

| Category | Example Architectures | Key Inductive Bias |
|---|---|---|
| **Feedforward** | MLP, Autoencoder | None — universal approximators |
| **Convolutional** | LeNet, AlexNet, VGG, ResNet, EfficientNet | Translation invariance; local features |
| **Recurrent** | RNN, LSTM, GRU, Bidirectional RNN | Sequential order; temporal dependencies |
| **Attention-Based** | Transformer, BERT, GPT, ViT | Global pairwise context; no locality bias |
| **Generative** | VAE, GAN, Diffusion Models, Flow Models | Data distribution modeling |
| **Graph-Based** | GCN, GAT, GraphSAGE | Permutation invariance; relational data |
| **Hybrid/Emerging** | Mamba, Spiking Neural Networks, MoE | Efficiency + scalability |

### Architectural Lineage

```
Perceptron (1958) → MLP (1986) → CNN (1998) → AlexNet (2012)
  → ResNet (2015) → Transformer (2017) → BERT/GPT (2018)
    → ViT (2020) → Diffusion Models (2020) → Mamba (2023)
```

Each step solved a specific failure mode of its predecessor:
- **ResNet** → solved vanishing gradients in very deep CNNs (skip connections)
- **Transformer** → solved the sequential bottleneck of RNNs (parallel attention)
- **ViT** → applied Transformers to images by treating patches as tokens
- **Diffusion Models** → solved GAN training instability via probabilistic denoising

---

## Learning Outcomes

- Built a comprehensive mental map of the deep learning landscape including architectures rarely covered in introductory courses (GNNs, Capsule Networks, Spiking Neural Networks, Mamba).
- Understood the **inductive biases** that make each architecture suited to its domain:
  - Translation invariance → CNN
  - Sequential memory → RNN/LSTM
  - Global context → Transformer
  - Relational structure → GNN
- Developed skills in communicating complex AI concepts visually to diverse audiences.
- Recognized the evolutionary lineage of architectures — how each innovation solved a specific failure mode of its predecessor.
- Understood why no architecture is universally best: the right model depends on data structure, available compute, and task.

---

## Project Files

| File | Description |
|---|---|
| `P02_Neural-Network-Zoo.pptx` | Full visual presentation (30+ architectures) |
| `P02_Neural-Network-Zoo.pdf` | PDF export of the presentation |
| `P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4` | 3D rotating showcase video |
| [`Convoshrimp/`](./Convoshrimp) | Interactive web app — browse the zoo live |
| [`Results-&-Visualizations/`](./Results-%26-Visualizations) | All slide screenshots (12 images) |

---

## Project Structure

```text
Project-02-Neural-Network-Zoo/
├── P02_Neural-Network-Zoo.pptx
├── P02_Neural-Network-Zoo.pdf
├── P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4
├── Results-&-Visualizations/
│   ├── 01.png
│   ├── 02.png
│   ├── 03.png
│   ├── 04.png
│   ├── 05.png
│   ├── 06.png
│   ├── 07.png
│   ├── 08.png
│   ├── 09.png
│   ├── 10.jpeg
│   ├── 11.png
│   └── 12.png
├── Convoshrimp/                         # Interactive web application
│   ├── index.html
│   ├── src/
│   ├── public/
│   ├── dist/
│   ├── package.json
│   ├── vite.config.js
│   ├── tailwind.config.js
│   ├── eslint.config.js
│   ├── postcss.config.js
│   ├── CHANGELOG.md
│   ├── CONTRIBUTING.md
│   ├── LICENSE
│   └── README.md
└── README.md
```

---

## Dependencies / Requirements

**To view the presentation:**
```
Microsoft PowerPoint 2016+ or Google Slides
```

**To view the video:**
```
Any video player (VLC, browser, QuickTime)
```

**To run the ConvoShrimp web app:**
```bash
cd Convoshrimp
npm install
npm run dev
```

---

## Data Access

This is a conceptual and visual project. No training datasets were used.

Key references:
- Asimov Institute Neural Network Zoo: [asimov.institute](https://www.asimovinstitute.org/neural-network-zoo/)
- Deep Learning textbook (Goodfellow, Bengio, Courville)
- Original papers: Vaswani et al. 2017 (Transformer), He et al. 2015 (ResNet), LeCun et al. 1998 (CNN)
