# Project 08 — Diffusion Models

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![Diffusion Models](https://img.shields.io/badge/architecture-Diffusion_Models-blueviolet.svg)
![Generative AI](https://img.shields.io/badge/topic-Generative_AI-ff69b4.svg)
![DDPM](https://img.shields.io/badge/model-DDPM-orange.svg)
![U-Net](https://img.shields.io/badge/architecture-U--Net-9cf.svg)
![Image Generation](https://img.shields.io/badge/task-Image_Generation-success.svg)
![Jupyter](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

This project implements and explores **Denoising Diffusion Probabilistic Models (DDPMs)** — the generative AI architecture that powers Stable Diffusion, DALL·E 2, Midjourney, and Imagen. Unlike GANs (which learn to fool a discriminator) or VAEs (which compress to a latent code), diffusion models learn to **reverse a gradual noising process** — starting from pure noise and iteratively denoising toward a coherent image.

The project covers the complete diffusion model pipeline: the **forward process** (adding Gaussian noise step-by-step until the image becomes noise), the **reverse process** (learning to predict and remove noise with a U-Net), and the **sampling pipeline** (generating new images from scratch through iterative denoising).

---

## Problem Statement

Generative AI has undergone a revolution with the rise of diffusion models, yet their mathematical foundations are often treated as a black box. GANs dominated image generation for years — but suffered from training instability and mode collapse. Diffusion models solved these problems through a principled probabilistic framework. This project asks: **How do diffusion models work from first principles, and can we implement the DDPM forward/reverse process to generate images?**

---

## Approach and Methodology

### The Forward Process (Diffusion)

The forward process gradually corrupts an image `x₀` over `T` timesteps by adding Gaussian noise at each step:

```
q(xₜ | xₜ₋₁) = N(xₜ; √(1 - βₜ) · xₜ₋₁, βₜ · I)
```

Where `β₁, β₂, ..., βT` is a **noise schedule** (variance of noise added at each step). After `T` steps, `xT` is approximately pure Gaussian noise — the image is fully destroyed.

**Key insight:** We can sample `xₜ` at any timestep directly from `x₀` without running all `t` steps:

```python
# Closed-form sampling at timestep t
alpha_bar_t = torch.prod(1 - betas[:t])
x_t = sqrt(alpha_bar_t) * x_0 + sqrt(1 - alpha_bar_t) * noise
```

### The Reverse Process (Denoising)

The reverse process learns to undo each denoising step using a **U-Net** neural network `εθ` that predicts the noise added at each step:

```
p_θ(xₜ₋₁ | xₜ) = N(xₜ₋₁; μθ(xₜ, t), Σθ(xₜ, t))
```

**Training objective:** Predict the noise `ε` that was added at timestep `t`, given the noisy image `xₜ` and the timestep `t`:

```python
loss = MSE(epsilon_theta(x_t, t), epsilon)  # Predict the actual noise
```

### U-Net Architecture

The denoising network is a **U-Net** with:
- **Encoder path:** Downsampling blocks that extract features at multiple scales.
- **Bottleneck:** Self-attention layers for global context.
- **Decoder path:** Upsampling blocks with skip connections from the encoder.
- **Time conditioning:** The timestep `t` is embedded and injected into each residual block, allowing the network to know "how noisy" the current input is.

### Sampling (Image Generation)

To generate a new image:
1. Start from pure Gaussian noise: `xT ~ N(0, I)`
2. Iteratively apply the reverse process for `T → 0`
3. Return `x₀` — the generated image

```python
x = torch.randn(batch_size, channels, height, width)  # Start: pure noise
for t in reversed(range(T)):
    predicted_noise = model(x, t)
    x = reverse_step(x, predicted_noise, t)
# x is now a generated image
```

### Noise Schedules Explored

| Schedule | Description | Trade-off |
|---|---|---|
| **Linear** | β increases linearly from β₁ to βT | Simple; destroys image too fast at end |
| **Cosine** | β follows a cosine curve | Smoother destruction; better sample quality |
| **Quadratic** | β increases quadratically | Aggressive early, slow late |

---

## Results and Evaluation

The project demonstrates the full diffusion pipeline:

**Forward Process Visualization:** An input image progressively degraded across 1000 timesteps — from sharp original → recognizable with noise → completely indistinguishable from random noise.

**Reverse Process (Denoising):** Starting from pure noise, the reverse process iteratively recovers structure — first recovering rough shapes and color blobs, then progressively sharpening detail.

**Generated Samples:** Novel images generated purely from random noise through the learned reverse process.

**Noise Schedule Comparison:** Cosine schedule produces significantly better sample quality than linear — the image degrades more gradually, giving the U-Net more signal to learn from at each step.

---

## Key Concepts Covered

| Concept | Description |
|---|---|
| **DDPM** | Denoising Diffusion Probabilistic Models (Ho et al., 2020) |
| **Forward Process** | Markov chain adding Gaussian noise over T steps |
| **Reverse Process** | Learned denoising via U-Net conditioned on timestep |
| **Noise Schedule** | Controls how noise is added — linear vs. cosine |
| **U-Net** | Encoder-decoder architecture with skip connections for denoising |
| **Score Matching** | Mathematical connection between diffusion and score-based generative models |
| **DDIM Sampling** | Deterministic sampling that requires far fewer steps (50 vs. 1000) |
| **Classifier-Free Guidance** | Conditioning diffusion on text/class labels without a separate classifier |

---

## Learning Outcomes

- Understood the **probabilistic framework** underlying diffusion models — Markov chains, Gaussian transitions, and variational lower bounds.
- Implemented the **forward process** using closed-form noise sampling at arbitrary timesteps.
- Built a **U-Net denoising network** conditioned on the diffusion timestep.
- Trained the model with the **simplified DDPM loss** (MSE on predicted noise).
- Implemented the **ancestral sampling** loop for image generation from noise.
- Compared **noise schedules** (linear vs. cosine) and understood their impact on generation quality.
- Connected DDPM to the broader landscape of generative models: VAEs, GANs, Flow Models, and Score-Based models.
- Understood the architecture path from DDPM → Latent Diffusion → Stable Diffusion.

---

## Project Files

```text
Project-08-Diffusion-Models/
├── P08_Diffusion-Models.ipynb        # Main Jupyter Notebook — full DDPM implementation
├── Results-&-Visualizations/         # Output images and generated samples
└── README.md                         # This file
```

| File | Description |
|---|---|
| `P08_Diffusion-Models.ipynb` | Full implementation: forward process, U-Net, training loop, and sampling |
| `Results-&-Visualizations/` | Noising sequences, generated image samples, noise schedule comparisons |

---

## Dependencies / Requirements

```bash
pip install torch torchvision numpy matplotlib tqdm jupyter
```

**Python:** 3.8+

```
torch >= 1.12
torchvision >= 0.13
numpy >= 1.21
matplotlib >= 3.5
tqdm >= 4.64
einops >= 0.4        # Optional: for cleaner tensor rearrangement
jupyter / Google Colab
```

> ⚠️ **GPU strongly recommended.** Training diffusion models is computationally intensive. Use Google Colab with a T4 or A100 GPU for reasonable training times.

---

## Running the Notebook

**Recommended: Google Colab with GPU**
1. Open [colab.research.google.com](https://colab.research.google.com)
2. Upload `P08_Diffusion-Models.ipynb`
3. Runtime → Change runtime type → **T4 GPU** (or A100 if available)
4. Run All Cells

```bash
# Local execution (GPU recommended):
pip install torch torchvision tqdm einops
jupyter notebook P08_Diffusion-Models.ipynb
```

---

## Data Access

The notebook uses standard benchmark datasets that load automatically — no manual download required.

**MNIST / Fashion-MNIST** (simple baseline for verifying the pipeline):
```python
from torchvision.datasets import MNIST, FashionMNIST
dataset = FashionMNIST(root='./data', train=True, download=True)
```

**CIFAR-10** (more complex — used for evaluating sample quality):
```python
from torchvision.datasets import CIFAR10
dataset = CIFAR10(root='./data', train=True, download=True)
```

**Further Reading:**
- Original DDPM Paper: [Ho et al., 2020 — arxiv.org/abs/2006.11239](https://arxiv.org/abs/2006.11239)
- Improved DDPM: [Nichol & Dhariwal, 2021 — arxiv.org/abs/2102.09672](https://arxiv.org/abs/2102.09672)
- Latent Diffusion (Stable Diffusion): [Rombach et al., 2022 — arxiv.org/abs/2112.10752](https://arxiv.org/abs/2112.10752)
