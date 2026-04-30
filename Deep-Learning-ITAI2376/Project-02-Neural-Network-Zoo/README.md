# Project 02 — Neural Network Zoo

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Deep Learning](https://img.shields.io/badge/topic-Deep_Learning-blueviolet.svg)
![Neural Networks](https://img.shields.io/badge/topic-Neural_Network_Architectures-orange.svg)
![Research](https://img.shields.io/badge/type-Visual_Showcase-lightgrey.svg)
![PowerPoint](https://img.shields.io/badge/tool-PowerPoint-B7472A.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

This project is a visual and conceptual exploration of the **Neural Network Zoo** — the full landscape of deep learning architectures that have shaped modern AI. Rather than focusing on a single model, the project maps the entire evolutionary tree of neural networks: from the original Perceptron and MLP through CNNs, RNNs, LSTMs, and Transformers, all the way to Generative Models, Graph Neural Networks, and beyond.

The centerpiece is a custom-designed **3D rotating architectural showcase** (`P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4`) themed around the Mantis Shrimp — an animal with 16 types of photoreceptors, chosen as a metaphor for how different neural architectures "see" data in fundamentally different ways.

---

## Problem Statement

Deep learning practitioners often develop tunnel vision — mastering one or two architectures while remaining unaware of the broader architectural landscape. This creates missed opportunities: applying a CNN where a GNN would excel, or using an MLP where sequence models are needed. This project asks: **What is the full map of neural network architectures, and what problem domain is each one designed to solve?**

---

## Approach and Methodology

- **Architecture Survey:** Catalogued and categorized 30+ neural network types, organized by their computational paradigm (feedforward, recurrent, convolutional, attention-based, generative, etc.).
- **Visual Design:** Created a polished PowerPoint presentation (`P02_Neural-Network-Zoo.pptx`) using custom graphics, metaphors, and visual hierarchy to communicate architectural complexity accessibly.
- **3D Video Showcase:** Produced a rotational 3D visualization video (`P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4`) that animates through the architecture zoo.
- **Mantis Shrimp Theme:** The visual design uses the Mantis Shrimp as a conceptual anchor — just as the shrimp processes light across 16 spectral channels simultaneously, deep learning architectures process data through multiple parallel pathways and representations.
- **ConvoShrimp Sub-Project:** The [`Convoshrimp/`](./Convoshrimp) interactive project is an extension that brings the neural network zoo to life as a browsable web application.

---

## Results and Evaluation

The project successfully mapped the complete neural network ecosystem across the following categories:

| Category | Example Architectures |
|---|---|
| **Feedforward** | MLP, Autoencoder |
| **Convolutional** | LeNet, AlexNet, VGG, ResNet, EfficientNet |
| **Recurrent** | RNN, LSTM, GRU, Bidirectional RNN |
| **Attention-Based** | Transformer, BERT, GPT, ViT |
| **Generative** | VAE, GAN, Diffusion Models |
| **Graph-Based** | GCN, GAT, GraphSAGE |
| **Hybrid/Emerging** | Mamba, Spiking Neural Networks |

---

## Learning Outcomes

- Built a comprehensive mental map of the deep learning landscape beyond commonly taught architectures.
- Understood the **inductive biases** that make each architecture suited to its domain (translation invariance → CNN; sequential memory → RNN; global context → Transformer).
- Developed skills in communicating complex AI concepts visually to diverse audiences.
- Recognized the evolutionary lineage of architectures — how each innovation solved a specific failure mode of its predecessor.

---

## Project Files

| File | Description |
|---|---|
| `P02_Neural-Network-Zoo.pptx` | Full visual presentation of the Neural Network Zoo |
| `P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4` | 3D rotating architecture showcase video |
| [`Convoshrimp/`](./Convoshrimp) | Interactive web app extension — browse the neural network zoo |

---

## Project Structure

```text
Project-02-Neural-Network-Zoo/
├── P02_Neural-Network-Zoo.pptx                                 # Full visual presentation
├── P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4
│                                                            # 3D rotating architecture video
├── Convoshrimp/                                               # Interactive web app
│   ├── src/                                                     # React source code
│   ├── public/
│   ├── package.json
│   └── README.md
└── README.md                                                  # Project documentation (this file)
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

**To run the ConvoShrimp web app** (see [`Convoshrimp/`](./Convoshrimp)):
```bash
cd Convoshrimp
npm install
npm run dev
```

---

## Data Access

This is a conceptual and visual project. No training datasets were used. All architecture diagrams and descriptions reference publicly available research papers and documentation.

Key references:
- Asimov Institute's Neural Network Zoo: [asimov.institute](https://www.asimovinstitute.org/neural-network-zoo/)
- Deep Learning textbook (Goodfellow, Bengio, Courville)
- Original papers for each architecture (Vaswani et al. 2017 for Transformer, He et al. 2015 for ResNet, etc.)
