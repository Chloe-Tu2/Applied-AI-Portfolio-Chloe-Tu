# Project 07 — RNNs vs. Transformers vs. Vision Transformers

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![RNN](https://img.shields.io/badge/architecture-RNN_LSTM_GRU-blue.svg)
![Transformer](https://img.shields.io/badge/architecture-Transformer-yellow.svg)
![Vision Transformer](https://img.shields.io/badge/architecture-Vision_Transformer_(ViT)-9cf.svg)
![CIFAR-10](https://img.shields.io/badge/dataset-CIFAR--10-lightblue.svg)
![Benchmark](https://img.shields.io/badge/type-Architecture_Benchmark-success.svg)
![Attention Maps](https://img.shields.io/badge/feature-Attention_Visualization-orange.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![CIFAR-10 Vision Transformer Overview](./Results-%26-Visualizations/CIFAR-10_Vision_Transformers_(ViTs).png)

This project is a **rigorous three-way architectural benchmark** comparing the three most influential families of deep learning sequence/spatial models on a single controlled task:

1. **Recurrent Neural Networks (RNNs)** — Vanilla RNN, LSTM, and GRU
2. **Transformers** — Self-attention based sequence models
3. **Vision Transformers (ViTs)** — Attention applied directly to image patches

Using the **CIFAR-10 dataset** (60,000 color images, 10 classes) as a common benchmark, the project evaluates each architecture across accuracy, training stability, convergence speed, and interpretability — building a comprehensive understanding of *why* the field moved from RNNs to Transformers to Vision Transformers.

A key feature of this project is the **attention map visualization** — showing exactly what parts of each image the Vision Transformer focuses on when making a prediction, including examples for deer, frog, truck, and bird.

---

## Problem Statement

The deep learning community has undergone a massive architectural shift over the last decade: from RNNs (dominant pre-2017) → Transformers (dominant post-2017) → Vision Transformers (dominant post-2020). But why? What specific limitations did each generation inherit, and what innovations solved them?

This project asks: **In a controlled experiment on the same dataset, how do RNN variants, Transformers, and Vision Transformers compare — and what do their failure modes reveal about architectural design principles?**

---

## Approach and Methodology

### Architecture 1: RNN Family (Vanilla RNN → LSTM → GRU)

CIFAR-10 images (32×32×3) were flattened into sequences (rows of pixels) to adapt RNNs for vision tasks.

- **Vanilla RNN:** Baseline sequential model with a single hidden state update per timestep. Demonstrates the vanishing gradient problem clearly — gradients shrink exponentially as they propagate through 1024 timesteps (32 rows × 32 pixels).
- **LSTM (Long Short-Term Memory):** Adds a cell state with input, forget, and output gates — allowing the model to selectively retain information across long sequences.
- **GRU (Gated Recurrent Unit):** Simplified LSTM with update and reset gates — comparable performance with fewer parameters.

### Architecture 2: Transformer

- Multi-head self-attention applied to flattened image patches (each row treated as a token).
- Position encodings added to provide spatial order context.
- Full encoder stack trained on CIFAR-10 classification with a CLS token.
- **Key difference from RNN:** All positions attend to all other positions simultaneously — no sequential bottleneck.

### Architecture 3: Vision Transformer (ViT)

- Images divided into fixed-size patches (4×4 on 32×32 CIFAR-10 → 64 patches).
- Each patch linearly projected to a D-dimensional embedding.
- Standard Transformer encoder with class token prepended.
- Trained with patch embeddings + position embeddings.

```python
# Patch embedding
patch_size = 4
num_patches = (32 // patch_size) ** 2  # 64 patches
patch_dim = 3 * patch_size * patch_size  # 48 values per patch

# Rearrange: (B, C, H, W) → (B, num_patches, patch_dim)
patches = rearrange(images, 'b c (h p1) (w p2) -> b (h w) (p1 p2 c)', p1=patch_size, p2=patch_size)
```

---

## Results & Visualizations

### CIFAR-10 Class Distribution

![Visualize Class Distribution](./Results-%26-Visualizations/Visualize_Class_Distribution.png)

### RNN Family Comparison

![Three-Way RNN Comparison — Vanilla RNN vs. LSTM vs. GRU](./Results-%26-Visualizations/Three-Way_RNN_Comparison_Vanilla_RNN_vs_LSTM_Vs_GRU.png)

![LSTM vs. GRU Detailed Comparison](./Results-%26-Visualizations/LSTM_vs_GRU_Comparison_Visualization.png)

### ViT Attention Maps — What Does the Model Focus On?

![Vision Transformer — What Does the Model Focus On?](./Results-%26-Visualizations/Vision_Transformer_what_Does_The_Model_Focus_on.png)

#### Per-Class Attention Map Examples

| **Attention Map — Deer**  | **Attention Map — Frog**  | **Attention Map — Bird** |
|:---:|:---:|:---:|
|![Attention Map for Deer](./Results-%26-Visualizations/Attention_Map_For_deer.png) | ![Attention Map for Frog](./Results-%26-Visualizations/Attention_Map_For-frog.png) | ![Attention Map for Bird](./Results-%26-Visualizations/Attention_map_for_bird.png) |

| **Attention Map — Truck** | *Attention Map — Automoblie** |
|:---:|:---:|
 | ![Attention Map for Truck](./Results-%26-Visualizations/Attention_map_for_Truck.png) | ![Visualizing ViT Attention Maps](./Results-%26-Visualizations/Visualizing_ViT_Attention.png) |
 
### Full Architecture Comparison

![Master Comparison Table — All Architectures](./Results-%26-Visualizations/Master_Comparison_Table.png)

![The Big Comparison — All Architectures Side-by-Side](./Results-%26-Visualizations/The_Big_Comparison_All_Architectures.png)

---

## Summary Results

| Architecture | CIFAR-10 Accuracy | Key Strength | Key Weakness |
|---|---|---|---|
| **Vanilla RNN** | ~45% | Simple, interpretable | Vanishing gradients; cannot see long context |
| **LSTM** | ~60% | Long-range dependencies via gating | Slow sequential training; parameter-heavy |
| **GRU** | ~58% | Efficient LSTM alternative | Similar sequential bottleneck limitations |
| **Transformer** | ~70% | Parallelizable; global attention | Needs large data; no spatial inductive bias |
| **Vision Transformer (ViT)** | ~75%+ | State-of-the-art; interpretable attention | Computationally expensive; data-hungry |

### Key Observations from Attention Maps

The ViT attention maps provide a window into what the model "sees":
- **Deer**: Attention concentrates on the body outline and head — semantic object regions
- **Frog**: Attention focuses on the face and distinctive coloring — discriminative features
- **Bird**: Attention maps to wing shape and silhouette — structural features
- **Truck**: Attention focuses on geometric edges and wheels — structural boundaries

This interpretability is a key advantage of Vision Transformers over CNNs and RNNs — the attention weights provide direct evidence of *what* the model is using to make its decision.

---

## Learning Outcomes

- Deeply understood the **vanishing gradient problem**: in a Vanilla RNN processing 1024 timesteps, gradients multiply by weights at each step — if weights are < 1, they shrink exponentially; if > 1, they explode. LSTM/GRU solve this with additive (not multiplicative) gradient paths through the cell state.
- Understood **self-attention** as a mechanism that computes pairwise relevance between all positions simultaneously: `Attention(Q, K, V) = softmax(QKᵀ / √d_k) · V`. No sequential computation → parallelizable → faster training.
- Learned how **ViT** adapts Transformers to vision by treating image patches as tokens — enabling the model to attend across spatially distant patches.
- Gained practical skills in **attention visualization** — extracting what a model "looks at" to make predictions, enabling human-interpretable AI.
- Developed rigorous **benchmark methodology**: controlling for architecture changes while holding data, task, evaluation metrics, and training budget constant.
- Understood the architectural progression: sequential (RNN) → parallel global (Transformer) → spatial parallel (ViT) — each solving the previous generation's core limitation.

---

## Project Structure

```text
Project-07-RNNs-vs-Transformers-vs-Vision-Transformers/
├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb      # Main Jupyter Notebook
├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.pdf        # PDF export of the notebook
├── Results-&-Visualizations/
│   ├── CIFAR-10_Vision_Transformers_(ViTs).png                # ViT on CIFAR-10 overview
│   ├── Visualize_Class_Distribution.png                       # CIFAR-10 class distribution
│   ├── Three-Way_RNN_Comparison_Vanilla_RNN_vs_LSTM_Vs_GRU.png # RNN family benchmark
│   ├── LSTM_vs_GRU_Comparison_Visualization.png               # LSTM vs GRU detailed
│   ├── Vision_Transformer_what_Does_The_Model_Focus_on.png    # ViT attention overview
│   ├── Visualizing_ViT_Attention.png                          # ViT attention visualization
│   ├── Attention_Map_For_deer.png                             # Attention map — deer
│   ├── Attention_Map_For-frog.png                             # Attention map — frog
│   ├── Attention_map_for_bird.png                             # Attention map — bird
│   ├── Attention_map_for_Truck.png                            # Attention map — truck
│   ├── Master_Comparison_Table.png                            # Full comparison metrics table
│   └── The_Big_Comparison_All_Architectures.png               # All architectures side-by-side
└── README.md
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
einops >= 0.4   # For ViT patch rearrangement operations
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
