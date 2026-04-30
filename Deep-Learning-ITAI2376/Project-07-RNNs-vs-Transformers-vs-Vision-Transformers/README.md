# Project 07 — RNNs vs. Transformers vs. Vision Transformers

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![RNN](https://img.shields.io/badge/architecture-RNN_LSTM_GRU-blue.svg)
![Transformer](https://img.shields.io/badge/architecture-Transformer-yellow.svg)
![Vision Transformer](https://img.shields.io/badge/architecture-Vision_Transformer_(ViT)-9cf.svg)
![CIFAR-10](https://img.shields.io/badge/dataset-CIFAR--10-lightblue.svg)
![Comparative Study](https://img.shields.io/badge/type-Architecture_Benchmark-success.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![CIFAR-10 Vision Transformer](./Results-%26-Visualizations/CIFAR-10_Vision_Transformers_(ViTs).png)

This project is a **rigorous three-way architectural benchmark** comparing the three most influential families of deep learning sequence/spatial models:

1. **Recurrent Neural Networks (RNNs)** — Vanilla RNN, LSTM, and GRU
2. **Transformers** — Self-attention based sequence models
3. **Vision Transformers (ViTs)** — Attention applied directly to image patches

Using the **CIFAR-10 dataset** as a common benchmark, the project evaluates each architecture family across accuracy, training stability, attention visualization, and conceptual design — building a comprehensive understanding of *why* the field moved from RNNs to Transformers.

---

## Problem Statement

The deep learning community has undergone a massive architectural shift — from RNNs (dominant pre-2017) to Transformers (dominant post-2017) to Vision Transformers (dominant post-2020). But why? What specific limitations did each generation inherit, and what innovations solved them? This project asks: **In a controlled experiment on the same dataset, how do RNN variants, Transformers, and Vision Transformers compare — and what do their failure modes reveal about architectural design?**

---

## Approach and Methodology

### Architecture 1: RNN Family (Vanilla RNN → LSTM → GRU)

- **Vanilla RNN:** Baseline sequential model; demonstrated the vanishing gradient problem.
- **LSTM (Long Short-Term Memory):** Cell state mechanism enabling long-range dependencies.
- **GRU (Gated Recurrent Unit):** Simplified gating mechanism — comparable performance to LSTM with fewer parameters.

Images treated as flattened sequences (rows of pixels) to adapt RNNs for vision tasks.

### Architecture 2: Transformers

- Multi-head self-attention applied to flattened image patches.
- Position encodings added to provide spatial context.
- Full encoder stack trained on CIFAR-10 classification.

### Architecture 3: Vision Transformers (ViT)

- Images divided into fixed-size patches (e.g., 4×4 on 32×32 CIFAR-10 images).
- Each patch linearly projected to an embedding.
- Standard Transformer encoder with class token for classification.
- **Attention map visualization:** What image regions does the ViT focus on?

---

## Results and Evaluation

![LSTM vs. GRU Comparison](./Results-%26-Visualizations/LSTM_vs_GRU_Comparison_Visualization.png)

![Three-Way RNN Comparison — Vanilla RNN vs. LSTM vs. GRU](./Results-%26-Visualizations/Three-Way_RNN_Comparison_Vanilla_RNN_vs_LSTM_Vs_GRU.png)

![Vision Transformer — What Does the Model Focus On?](./Results-%26-Visualizations/Vision_Transformer_what_Does_The_Model_Focus_on.png)

![Visualizing ViT Attention Maps](./Results-%26-Visualizations/Visualizing_ViT_Attention.png)

![Class Distribution Visualization](./Results-%26-Visualizations/Visualize_Class_Distribution.png)

![Master Comparison Table — All Architectures](./Results-%26-Visualizations/Master_Comparison_Table.png)

![The Big Comparison — All Architectures](./Results-%26-Visualizations/The_Big_Comparison_All_Architectures.png)

**Summary Results:**

| Architecture | CIFAR-10 Accuracy | Key Strength | Key Weakness |
|---|---|---|---|
| **Vanilla RNN** | ~45% | Simple, interpretable | Vanishing gradients; can't see long context |
| **LSTM** | ~60% | Long-range dependencies | Slow training; sequential bottleneck |
| **GRU** | ~58% | Efficient LSTM alternative | Similar limitations to LSTM |
| **Transformer** | ~70% | Parallelizable; global attention | Needs large data; no inductive bias |
| **Vision Transformer (ViT)** | ~75%+ | State-of-the-art; patch-based attention | Computationally expensive; data-hungry |

---

## Learning Outcomes

- Deeply understood the **vanishing gradient problem** and how LSTM/GRU solve it with gating mechanisms.
- Understood **self-attention** as a mechanism for computing pairwise relationships between all positions simultaneously.
- Learned how **ViT** adapts the Transformer paradigm to vision by treating image patches as tokens.
- Gained practical skills in **attention visualization** — extracting what a model "looks at" to make predictions.
- Developed rigorous benchmark methodology: controlling for architecture changes while holding data, task, and evaluation metrics constant.

---

## Project Structure

```text
Project-07-RNNs-vs-Transformers-vs-Vision-Transformers/
├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb      # Main Jupyter Notebook
├── Results-&-Visualizations/                                  # Output images and plots
│   ├── CIFAR-10_Vision_Transformers_(ViTs).png                # ViT on CIFAR-10 visualization
│   ├── LSTM_vs_GRU_Comparison_Visualization.png               # LSTM vs GRU comparison
│   ├── Three-Way_RNN_Comparison_Vanilla_RNN_vs_LSTM_Vs_GRU.png
│   │                                                          # RNN family benchmark
│   ├── Vision_Transformer_what_Does_The_Model_Focus_on.png    # ViT attention maps
│   ├── Visualizing_ViT_Attention.png                          # ViT attention visualization
│   ├── Visualize_Class_Distribution.png                       # CIFAR-10 class distribution
│   ├── Master_Comparison_Table.png                            # Full comparison metrics table
│   └── The_Big_Comparison_All_Architectures.png               # All architectures side-by-side
└── README.md                                                  # Project documentation (this file)
```

---

## Dependencies / Requirements

```bash
pip install torch torchvision tensorflow numpy matplotlib seaborn einops jupyter
```

**Python:** 3.8+

```
torch >= 1.12
torchvision >= 0.13
tensorflow >= 2.10
numpy >= 1.21
matplotlib >= 3.5
seaborn >= 0.11
einops >= 0.4  # For ViT patch operations
jupyter / Google Colab
```

---

## Running the Notebook

**Recommended: Google Colab with GPU**
1. Open [colab.research.google.com](https://colab.research.google.com)
2. Upload `P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb`
3. Runtime → Change runtime type → T4 GPU
4. Run All Cells (~30-60 min with GPU)

```bash
# Local execution:
pip install torch torchvision einops
jupyter notebook P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb
```

---

## Data Access

**CIFAR-10** loads directly within the notebook — no manual download required:

```python
import torchvision
train_dataset = torchvision.datasets.CIFAR10(root='./data', train=True, download=True)
```

**Dataset Details:**
- **Images:** 60,000 color images (50k train / 10k test)
- **Size:** 32×32 pixels, 3 channels (RGB)
- **Classes:** 10 (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck)
- **Source:** [cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)
- **Download size:** ~170MB (automatic via PyTorch/TensorFlow)
