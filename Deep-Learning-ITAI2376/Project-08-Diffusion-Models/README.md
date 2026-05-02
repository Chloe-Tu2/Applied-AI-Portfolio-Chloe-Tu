# Project 08 — Diffusion Models

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![Diffusion Models](https://img.shields.io/badge/architecture-Diffusion_Models-blueviolet.svg)
![Generative AI](https://img.shields.io/badge/topic-Generative_AI-ff69b4.svg)
![DDPM](https://img.shields.io/badge/model-DDPM-orange.svg)
![U-Net](https://img.shields.io/badge/architecture-U--Net-9cf.svg)
![Image Generation](https://img.shields.io/badge/task-Image_Generation-success.svg)
![Google Colab](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

This project implements and explores **Denoising Diffusion Probabilistic Models (DDPMs)** — the generative AI architecture that powers Stable Diffusion, DALL·E 2, Midjourney, and Imagen. Unlike GANs (which learn to fool a discriminator) or VAEs (which compress to a latent code), diffusion models learn to **reverse a gradual noising process** — starting from pure Gaussian noise and iteratively denoising toward a coherent image.

The project covers the complete diffusion model pipeline from scratch:
- **Forward process**: Adding Gaussian noise step-by-step until the image becomes noise
- **Reverse process**: Learning to predict and remove noise using a U-Net conditioned on the diffusion timestep
- **Sampling**: Generating brand-new images purely from random noise via the learned reverse process

The project generates multiple digits (0-9) and visualizes the full generation sequence from noise to finished image.

---

## Problem Statement

Generative AI has undergone a revolution with diffusion models, yet their mathematical foundations are often treated as a black box. GANs dominated image generation for years — but suffered from training instability (mode collapse, discriminator dominance) and poor mode coverage. Diffusion models solved these problems through a principled probabilistic framework grounded in non-equilibrium thermodynamics.

This project asks: **How do diffusion models work from first principles, and can we implement the DDPM forward/reverse process to generate novel images?**

---

## Approach and Methodology

### The Forward Process (Diffusion)

The forward process gradually corrupts an image `x₀` over `T` timesteps by adding Gaussian noise at each step:

```
q(xₜ | xₜ₋₁) = N(xₜ; √(1 - βₜ) · xₜ₋₁, βₜ · I)
```

Where `β₁, β₂, ..., βT` is a **noise schedule**. After `T` steps, `xT` ≈ pure Gaussian noise.

**Key insight:** Sampling `xₜ` at any timestep directly from `x₀` (closed form):
```python
alpha_bar_t = torch.prod(1 - betas[:t])
x_t = sqrt(alpha_bar_t) * x_0 + sqrt(1 - alpha_bar_t) * noise
```

### The Reverse Process (Denoising U-Net)

The U-Net `εθ` learns to predict the noise added at each timestep:

```python
loss = MSE(epsilon_theta(x_t, t), epsilon)  # Predict the actual noise
```

**U-Net Architecture:**
- **Encoder path**: Downsampling blocks (Conv → BN → ReLU) extracting features at multiple scales
- **Bottleneck**: Self-attention layers for global context
- **Decoder path**: Upsampling blocks with skip connections from encoder
- **Time conditioning**: Timestep `t` embedded and injected into each residual block

### Sampling (Image Generation)

```python
x = torch.randn(batch_size, channels, H, W)  # Start: pure noise
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

## Results & Visualizations

### Training Progress

![Diffusion Model Training Progress](./Results-%26-Visualizations/Diffusion_Model_Training_Progress.png)

### Loss Curves

![Training and Validation Loss](./Results-%26-Visualizations/Training_and_Validation_Loss.png)

![Training and Validation Loss — Run 01](./Results-%26-Visualizations/Training_and_Validation_Loss_01.png)

![Final Training and Validation Loss](./Results-%26-Visualizations/Final_Training_and_Validation_Loss.png)

![Smoothed Training and Validation Loss — Val/Train Ratio](./Results-%26-Visualizations/Smoothed_Training_and_Validation_Loss_Vali-Train_Loss_Ratio.png)

### Generated Samples

![Final Generated Samples](./Results-%26-Visualizations/Final_Generated_samples.png)

![Generated Samples Visual Progress](./Results-%26-Visualizations/Generated_samples_Visual_progress.png)

![Generated Samples Epoch 50 (A)](./Results-%26-Visualizations/Generated_samples_Epoch_50-50_01.png)

![Generated Samples Epoch 50 (B)](./Results-%26-Visualizations/Generated_sampls_Epoch_50-50_.png)

### Generation Watching — Step-by-Step Denoising

![Watching the Generation Process — Step 01](./Results-%26-Visualizations/Watching_the_Generation_Process_01.png)

![Watching the Generation Process — Step 02](./Results-%26-Visualizations/Watching_the_Generation_Process_02.png)

![Watching the Generation Process — Step 03](./Results-%26-Visualizations/Watching_the_Generation_Process_03.png)

### Conditional Generation — 4 Versions of Each Digit (0–9)

![4 Versions of Number 01](./Results-%26-Visualizations/Generating_4_versions_of_number_01.png)

![4 Versions of Number 02](./Results-%26-Visualizations/Generating_4_versions_of_number_02.png)

![4 Versions of Number 03](./Results-%26-Visualizations/Generating_4_versions_of_number_03.png)

![4 Versions of Number 04](./Results-%26-Visualizations/Generating_4_versions_of_number_04.png)

![4 Versions of Number 05](./Results-%26-Visualizations/Generating_4_versions_of_number_05.png)

![4 Versions of Number 06](./Results-%26-Visualizations/Generating_4_versions_of_number_06.png)

![4 Versions of Number 07](./Results-%26-Visualizations/Generating_4_versions_of_number_07.png)

![4 Versions of Number 08](./Results-%26-Visualizations/Generating_4_versions_of_number_08.png)

![4 Versions of Number 09](./Results-%26-Visualizations/Generating_4_versions_of_number_09.png)

![4 Versions of Number 10](./Results-%26-Visualizations/Generating_4_versions_of_number_10.png)

### Visualization Function — Dog Generation Sample

![Visualization Function Dogs](./Results-%26-Visualizations/Visualization_function_dogs.png)

### Top-1 to Top-3 Scores

![Top 1-3 Score](./Results-%26-Visualizations/Top_1-3_Score.png)

---

## Key Concepts Covered

| Concept | Description |
|---|---|
| **DDPM** | Denoising Diffusion Probabilistic Models (Ho et al., 2020) |
| **Forward Process** | Markov chain adding Gaussian noise over T steps |
| **Reverse Process** | Learned denoising via U-Net conditioned on timestep |
| **Noise Schedule** | Controls how noise is added — linear vs. cosine |
| **U-Net** | Encoder-decoder architecture with skip connections |
| **Score Matching** | Mathematical connection to score-based generative models |
| **DDIM Sampling** | Deterministic sampling (50 steps vs. 1000) |
| **Classifier-Free Guidance** | Conditioning diffusion on class labels without a separate classifier |

---

## Learning Outcomes

- Understood the **probabilistic framework** underlying diffusion models — Markov chains, Gaussian transitions, and the variational lower bound.
- Implemented the **forward process** using closed-form noise sampling at arbitrary timesteps — enabling efficient training without simulating all `T` steps.
- Built a **U-Net denoising network** conditioned on the diffusion timestep using learned sinusoidal embeddings.
- Trained the model with the **simplified DDPM loss** (MSE on predicted noise) — significantly simpler than the full ELBO.
- Implemented the **ancestral sampling** loop for image generation from pure noise.
- Compared **noise schedules** (linear vs. cosine) and understood their impact on generation quality.
- Connected DDPM to the broader landscape of generative models: VAEs → GANs → Flow Models → DDPMs → Latent Diffusion (Stable Diffusion).
- Understood the architectural path: DDPM (pixel space) → LDM (latent space) → Stable Diffusion (text-conditioned LDM).

---

## Project Structure

```text
Project-08-Diffusion-Models/
├── P08_Diffusion-Models.ipynb                                 # Main Jupyter Notebook
├── P08_Diffusion-Models.pdf                                   # PDF export of the notebook
├── Results-&-Visualizations/
│   ├── Diffusion_Model_Training_Progress.png
│   ├── Training_and_Validation_Loss.png
│   ├── Training_and_Validation_Loss_01.png
│   ├── Final_Training_and_Validation_Loss.png
│   ├──STUDENT_ACTIVITY_Generating_numbers_with_different_noise_seeds.png
│   ├── Smoothed_Training_and_Validation_Loss_Vali-Train_Loss_Ratio.png
│   ├── Final_Generated_samples.png
│   ├── Generated_samples_Visual_progress.png
│   ├── Generated_samples_Epoch_50-50_01.png
│   ├── Generated_sampls_Epoch_50-50_.png
│   ├── Generating New Images_01_Digits.png
│   ├── Watching_the_Generation_Process_01.png
│   ├── Watching_the_Generation_Process_02.png
│   ├── Watching_the_Generation_Process_03.png
│   ├── Generating_4_versions_of_number_01.png
│   ├── Generating_4_versions_of_number_02.png
│   ├── Generating_4_versions_of_number_03.png
│   ├── Generating_4_versions_of_number_04.png
│   ├── Generating_4_versions_of_number_05.png
│   ├── Generating_4_versions_of_number_06.png
│   ├── Generating_4_versions_of_number_07.png
│   ├── Generating_4_versions_of_number_08.png
│   ├── Generating_4_versions_of_number_09.png
│   ├── Generating_4_versions_of_number_10.png
│   ├── Visualization_function_dogs.png
│   └── Top_1-3_Score.png
└── README.md
```

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
einops >= 0.4        # Optional: for tensor rearrangement
jupyter / Google Colab
```

> ⚠️ **GPU strongly recommended.** Training diffusion models is computationally intensive. Use Google Colab with a T4 or A100 GPU.

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

Standard benchmark datasets — no manual download required.

**MNIST / Fashion-MNIST** (pipeline validation):
```python
from torchvision.datasets import MNIST, FashionMNIST
dataset = FashionMNIST(root='./data', train=True, download=True)
```

**CIFAR-10** (sample quality evaluation):
```python
from torchvision.datasets import CIFAR10
dataset = CIFAR10(root='./data', train=True, download=True)
```

**Further Reading:**
- Original DDPM Paper: [Ho et al., 2020 — arxiv.org/abs/2006.11239](https://arxiv.org/abs/2006.11239)
- Improved DDPM: [Nichol & Dhariwal, 2021 — arxiv.org/abs/2102.09672](https://arxiv.org/abs/2102.09672)
- Latent Diffusion (Stable Diffusion): [Rombach et al., 2022 — arxiv.org/abs/2112.10752](https://arxiv.org/abs/2112.10752)
