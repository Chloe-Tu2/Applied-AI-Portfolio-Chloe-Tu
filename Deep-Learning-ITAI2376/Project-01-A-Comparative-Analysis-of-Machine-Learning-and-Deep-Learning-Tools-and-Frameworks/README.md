# Project 01 — A Comparative Analysis of ML & DL Tools and Frameworks

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Deep Learning](https://img.shields.io/badge/topic-Deep_Learning-blueviolet.svg)
![Machine Learning](https://img.shields.io/badge/topic-Machine_Learning-orange.svg)
![Research](https://img.shields.io/badge/type-Research_%26_Analysis-lightgrey.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-orange.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![Scikit-Learn](https://img.shields.io/badge/library-Scikit--Learn-F7931E.svg)
![JAX](https://img.shields.io/badge/library-JAX-9cf.svg)
![Fast.ai](https://img.shields.io/badge/library-Fast.ai-green.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

This project delivers a comprehensive comparative analysis of the dominant tools and frameworks used in Machine Learning and Deep Learning. Rather than treating frameworks as interchangeable black boxes, this study examines the philosophical differences, practical trade-offs, and real-world use cases of each major platform — from classical ML libraries to cutting-edge deep learning ecosystems.

The analysis spans six major frameworks: **TensorFlow**, **PyTorch**, **Keras**, **Scikit-Learn**, **JAX**, and **Fast.ai** — evaluating each across multiple dimensions including ease of use, performance, deployment capability, community adoption, research relevance, and hardware compatibility.

This project serves as a foundational reference document for all subsequent work in this course: understanding *which tool to use, and why*, before reaching for any framework.

---

## Problem Statement

The AI/ML landscape is fragmented across numerous competing frameworks, each with distinct design philosophies, community support, and performance characteristics. A practitioner entering the field faces a genuine decision problem: TensorFlow or PyTorch? Keras or raw TensorFlow? JAX or NumPy? Scikit-Learn or a deep learning framework for tabular data?

These choices have real consequences: the wrong framework for a task creates unnecessary complexity, slower iteration, harder debugging, and poor production deployment. This project asks: **What are the meaningful differences between today's ML/DL tools, and how should a practitioner choose between them for a given task?**

---

## Approach and Methodology

### Framework Survey
Systematically surveyed all major ML/DL libraries used in research and industry as of 2024, gathering data from official documentation, benchmark papers, community surveys (e.g., Stack Overflow Developer Survey, Papers With Code stats), and hands-on experimentation.

### Criteria-Based Comparison
Evaluated each framework across a structured rubric:

| Evaluation Axis | What It Measures |
|---|---|
| **Ease of Use** | Learning curve, API clarity, documentation quality |
| **Performance** | Training speed, memory efficiency, hardware support |
| **Deployment** | Mobile (TFLite), edge (ONNX), cloud (TFServing, TorchServe) |
| **Community** | GitHub stars, Stack Overflow activity, tutorials, job market |
| **Research Adoption** | Share of top-venue ML papers (NeurIPS, ICML, ICLR) |
| **Flexibility** | Ability to customize loss, layers, training loops, gradients |

### Use-Case Mapping
Each framework was mapped to its optimal use case rather than ranked universally — acknowledging that the "best" framework depends on the task, team, and deployment target.

### Historical Context
Traced the full evolutionary arc of ML/DL tooling:
- **Pre-2012:** Manual feature engineering + Scikit-Learn (SVM, Random Forest, Logistic Regression)
- **2012–2016:** Theano + Caffe — first-generation GPU-accelerated deep learning
- **2016–2017:** TensorFlow 1.x (static graphs) + Keras (high-level wrapper)
- **2017–2019:** PyTorch 1.x — dynamic graphs reshape research workflows
- **2019–present:** TensorFlow 2.x eager mode, JAX, Fast.ai, and the Hugging Face ecosystem

---

## Results and Evaluation

Key findings from the comparative analysis:

| Framework | Best For | Key Strength | Key Limitation |
|---|---|---|---|
| **Scikit-Learn** | Classical ML (tabular data) | Unified API, rapid prototyping, pipeline integration | Not designed for deep learning or GPU acceleration |
| **TensorFlow / Keras** | Production & Mobile deployment | TFLite, TFServing, Keras high-level API | More verbose than PyTorch for research |
| **PyTorch** | Research, NLP, RL | Dynamic graphs, Hugging Face ecosystem, Pythonic debugging | Deployment infrastructure less mature than TF |
| **JAX** | Custom accelerators, research | XLA compilation, functional transforms, vmap/jit | Steep learning curve; no high-level API by default |
| **Fast.ai** | Education & rapid prototyping | High-level API over PyTorch; excellent defaults | Opinionated; harder to customize deeply |
| **Keras (standalone)** | Beginners & quick models | Simplest API; multi-backend (TF, PyTorch, JAX) | Less flexible for low-level customization |

### Key Statistical Finding
Research paper adoption data reveals the field's direction:
- **PyTorch** powers approximately **75% of papers** at top ML conferences (NeurIPS, ICML, ICLR) as of 2023.
- **TensorFlow** maintains dominance in **enterprise production** pipelines due to mature serving and mobile deployment tooling.
- **JAX** is rapidly growing in research, particularly for reinforcement learning and custom hardware.

### Framework Decision Framework

The analysis produced a practical decision guide for practitioners:

```
Task → Recommended Framework
─────────────────────────────────────────────────────
Tabular data (SVM, RF, XGBoost)  → Scikit-Learn
Training & research (NLP, CV, RL) → PyTorch
Production deployment (mobile/edge) → TensorFlow + Keras
Custom GPU kernels & research math  → JAX
Education & teaching               → Fast.ai or Keras
Fine-tuning LLMs / Transformers    → Hugging Face + PyTorch
```

---

## Learning Outcomes

- Gained a structured mental model for navigating the ML/DL framework ecosystem without being misled by hype or popularity alone.
- Understood the fundamental distinction between **static computation graphs** (TensorFlow 1.x — define-then-run) and **dynamic computation graphs** (PyTorch, TensorFlow 2.x eager mode — define-by-run). Dynamic graphs allow Python-native debugging and flexible control flow, which transformed the research workflow.
- Learned why **automatic differentiation** is the core value proposition of deep learning frameworks — replacing hand-coded gradient derivations with `loss.backward()`.
- Developed the ability to evaluate frameworks based on project requirements (research vs. production, small team vs. enterprise, CPU vs. GPU vs. TPU) rather than popularity alone.
- Established foundational vocabulary — computation graphs, eager mode, XLA compilation, ONNX export, quantization, model serving — that underpins all subsequent deep learning projects.
- Understood the Hugging Face ecosystem as a distribution layer on top of PyTorch/TensorFlow, enabling rapid adoption of state-of-the-art pre-trained models.

---

## Project Files

| File | Description |
|---|---|
| `P01_A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks.pdf` | Full research report and comparative analysis |

---

## Project Structure

```text
Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks/
├── P01_A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks.pdf
│                                      # Full research report: framework survey, comparison tables,
│                                      # use-case mapping, and practitioner decision framework
└── README.md                          # Project documentation (this file)
```

---

## Dependencies / Requirements

This is a research and analysis project. No code execution is required.

**To view the report:**
- Any PDF viewer (Adobe Acrobat, browser, Preview, or any OS-native PDF reader)

---

## Data Access

This project is a conceptual and analytical report. No datasets were used for model training. All frameworks and tools discussed are publicly available and open-source.

- **TensorFlow:** [tensorflow.org](https://tensorflow.org)
- **PyTorch:** [pytorch.org](https://pytorch.org)
- **Scikit-Learn:** [scikit-learn.org](https://scikit-learn.org)
- **Keras:** [keras.io](https://keras.io)
- **JAX:** [github.com/google/jax](https://github.com/google/jax)
- **Fast.ai:** [fast.ai](https://fast.ai)
- **Papers With Code Framework Stats:** [paperswithcode.com/trends](https://paperswithcode.com/trends)

---

## Course Context

This project is the foundation of ITAI-2376: Deep Learning. Understanding the tool landscape before diving into implementations ensures every subsequent project uses the right framework for the right reason — a habit that distinguishes principled practitioners from framework followers.
