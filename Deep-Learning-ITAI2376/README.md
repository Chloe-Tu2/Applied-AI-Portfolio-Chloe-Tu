# ITAI-2376: Deep Learning

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![Keras](https://img.shields.io/badge/framework-Keras-D00000.svg)
![Hugging Face](https://img.shields.io/badge/library-Hugging_Face-yellow.svg)
![OpenAI Gym](https://img.shields.io/badge/environment-OpenAI_Gym-00BFFF.svg)
![Transformers](https://img.shields.io/badge/architecture-Transformers-9cf.svg)
![Vision Transformers](https://img.shields.io/badge/architecture-Vision_Transformers_(ViT)-blueviolet.svg)
![Reinforcement Learning](https://img.shields.io/badge/topic-Reinforcement_Learning-orange.svg)
![CrewAI](https://img.shields.io/badge/framework-CrewAI-4B0082.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![Google Colab](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

---

## Course Overview

**Institution:** Houston City College  
**Course:** ITAI-2376 Deep Learning  
**Focus:** Neural Architectures, Sequence Models, Transformers & Autonomous Agents

This course delivers a rigorous, project-driven exploration of modern deep learning — from implementing neural networks by hand using NumPy, to deploying production-ready multi-agent AI systems. Each project builds on the last, progressively mastering more complex architectures and paradigms: CNNs for vision, Transformers for language, Vision Transformers for spatial attention, Reinforcement Learning for autonomous decision-making, and finally multi-agent AI pipelines for real-world cybersecurity applications.

* **Hands-on Implementation:** Every concept is implemented in code — no black-box APIs.
* **Architecture Breadth:** RNNs → LSTMs → GRUs → Transformers → ViTs → Reinforcement Learning → Multi-Agent AI.
* **Creative Application:** Projects include NLP analysis of the film *Arrival*, a puppy-vs-bagel CNN challenge, and a Heptapod alien language generator.
* **Capstone:** A full multi-agent phishing detection system using CrewAI with autonomous escalation and threat memory.

---

## Featured Capstone Project

### [The Hunter — Automated Email Phishing Defense & Detection System](./The-Hunter-Automated-Email-Phishing-Defense-Detection-System)
**Multi-Agent AI | CrewAI | Deep Learning | NLP | Cybersecurity**

![The Hunter Interface](./The-Hunter-Automated-Email-Phishing-Defense-Detection-System/results/demo_visualizations/The_Hunter_Interface.png)

A production-ready **multi-agent AI system** that autonomously analyzes, classifies, and responds to email phishing threats. Built with **CrewAI**, the system deploys three specialized agents operating in a coordinated pipeline:

* **Agent 1 — The Analyst:** Scans email content using a trained **BiLSTM + Random Forest Ensemble** classifier, computing a numeric phishing risk score.
* **Agent 2 — The Arbiter:** Autonomously decides whether to quarantine, flag, or clear the email based on the risk score. **Agentic behavior:** auto-escalates borderline cases without human input.
* **Agent 3 — The Archivist:** Maintains a **persistent threat memory database** — if the same sender has been flagged before, the agent automatically increases the threat level. **Agentic behavior:** repeat-offender detection with cross-session memory.

**Key Technical Achievements:**
* Ensemble model (BiLSTM + Random Forest) achieving **97%+ detection accuracy** on the Alam Phishing Dataset.
* Fully autonomous pipeline — no human intervention needed for classification and quarantine decisions.
* Persistent SQLite threat memory enabling longitudinal tracking across multiple sessions.
* Complete React-based web app interface (`The-Hunter`) for real-time email submission and analysis.

---

## Project Directory

### 🔹 Phase 1: Foundations & Frameworks

* **[Project 01: Comparative Analysis — ML & DL Tools](./Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks)**
    * *Focus:* Framework Survey & Decision Framework.
    * *Description:* Systematic comparison of TensorFlow, PyTorch, Keras, Scikit-Learn, JAX, and Fast.ai — evaluating ease of use, performance, deployment, and research adoption.
    * *Topics Covered:* Static vs. dynamic computation graphs, framework selection criteria, production vs. research trade-offs, historical evolution from Theano/Caffe to modern ecosystems.

* **[Project 02: Neural Network Zoo](./Project-02-Neural-Network-Zoo)**
    * *Focus:* Architecture Landscape & Visual Taxonomy.
    * *Description:* A comprehensive visual map of 30+ neural network architectures, themed around the Mantis Shrimp — an organism with 16 photoreceptor types, used as a metaphor for multi-modal perception. Includes a 3D rotating showcase video and the **[ConvoShrimp](./Project-02-Neural-Network-Zoo/Convoshrimp)** interactive web app.
    * *Topics Covered:* Feedforward, convolutional, recurrent, attention-based, generative, graph, and hybrid architectures. Inductive biases and architectural lineage.

### 🔹 Phase 2: Building & Training Neural Networks

* **[Project 03: Neural Networks from Scratch to Frameworks](./Project-03-Neural-Networks-from-Scratch-to-Frameworks)**
    * *Focus:* Forward propagation, backpropagation, and framework internals.
    * *Description:* Built a complete neural network using only NumPy (no ML libraries), then rebuilt the same model in TensorFlow/Keras — directly comparing implementation complexity and performance on Fashion-MNIST.
    * *Topics Covered:* Matrix multiplication, ReLU/Softmax activation, manual gradient computation via chain rule, Keras Sequential API, automatic differentiation.
    * *Key Libraries:* `NumPy`, `TensorFlow`, `Keras`, `Matplotlib`.

* **[Project 04: Deep Learning for an 11-Year-Old](./Project-04-Deep-Learning-for-an-11-year-old)**
    * *Focus:* Science Communication & Educational AI.
    * *Description:* Explains all core deep learning concepts through age-appropriate analogies, and brings them to life in the **[Neural-Network-Squad](./Project-04-Deep-Learning-for-an-11-year-old/Neural-Network-Squad)** interactive web application — a live, visual neural network simulator.
    * *Topics Covered:* Neurons, layers, training, loss, backpropagation, activation functions — all communicated without jargon.

### 🔹 Phase 3: Convolutional & Vision Models

* **[Project 05: CNN — Puppy or Bagel?](./Project-05-CNN-Puppy-or-Bagel)**
    * *Focus:* Transfer Learning & Inter-Class Visual Similarity.
    * *Description:* Built a ResNet50-powered CNN to tackle the internet's most delightful visual challenge: distinguishing golden retriever puppies from golden sesame bagels. A rigorous exploration of why inter-class similarity breaks naive classifiers.
    * *Topics Covered:* Transfer Learning (feature extraction → fine-tuning), ResNet50 architecture, data augmentation, confusion matrix analysis.
    * *Key Libraries:* `TensorFlow`, `Keras`, `NumPy`, `Matplotlib`.

### 🔹 Phase 4: Sequence Models & Transformers

* **[Project 06: Analyzing *Arrival* Through the Lens of NLP](./Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP)**
    * *Focus:* BERT, Self-Attention, Semantic Similarity & Creative AI.
    * *Description:* **Project Heptapod** — applies BERT embeddings, attention visualization, and a custom Heptapod logogram generator to analyze the alien language in Denis Villeneuve's *Arrival*. A creative exploration of how language structure shapes cognition.
    * *Topics Covered:* Bidirectional Transformers (BERT), multi-head attention, semantic embeddings, cosine similarity, the Sapir-Whorf hypothesis computationally modeled.
    * *Key Libraries:* `Transformers`, `PyTorch`, `Matplotlib`, `Seaborn`.

* **[Project 07: RNNs vs. Transformers vs. Vision Transformers](./Project-07-RNNs-vs-Transformers-vs-Vision-Transformers)**
    * *Focus:* Three-way architecture benchmark on CIFAR-10.
    * *Description:* A rigorous controlled experiment comparing Vanilla RNN, LSTM, GRU, Transformer, and Vision Transformer (ViT) architectures on the same task — revealing exactly why the field shifted from recurrent models to attention-based ones, with full attention map visualization.
    * *Topics Covered:* Vanishing gradients, LSTM/GRU gating, self-attention, patch embeddings, ViT attention maps, comparative benchmarking.
    * *Key Libraries:* `PyTorch`, `TorchVision`, `einops`, `Matplotlib`.

### 🔹 Phase 5: Reinforcement Learning

* **[Project 09: Teach an Agent to Balance a Pole](./Project-09-Teach-an-Agent-to-Balance-a-Pole)**
    * *Focus:* Q-Learning, Reinforcement Learning Fundamentals.
    * *Description:* Implemented a Q-Learning agent from scratch to solve the CartPole-v1 environment — going from a random baseline (~8 steps) to a converged policy achieving 200-500+ steps through pure trial-and-error learning.
    * *Topics Covered:* Markov Decision Processes (MDPs), Bellman equation, Q-table construction, epsilon-greedy exploration, state discretization, exploration vs. exploitation.
    * *Key Libraries:* `Gymnasium`, `NumPy`, `Matplotlib`.

---

## Notebooks Content Overview

Each notebook in this repository is a comprehensive educational resource:

* **Well-Documented Code:** Markdown explanations accompany every code block — explaining the *why*, not just the *how*.
* **Executable Pipelines:** End-to-end workflows from data loading to model evaluation, ready to run on Google Colab.
* **Rich Visualizations:**
    * Training vs. Validation Loss/Accuracy curves.
    * Confusion Matrices and classification reports.
    * Attention heatmaps and architecture diagrams.
    * Reinforcement learning reward curves and episode replays.
* **Architecture Deep Dives:** Each notebook includes a conceptual explanation of the model architecture before implementation.
* **PDF Reports:** Full project reports available as PDFs for offline review.

---

## Datasets Used

| Project | Dataset | Classes | Size | Access |
|---|---|---|---|---|
| **Project 03** | Fashion-MNIST | 10 clothing categories | 70,000 images | Auto via `keras.datasets` |
| **Project 05** | Puppy vs. Bagel | 2 (Puppy / Bagel) | Custom curated | Notebook instructions |
| **Project 06** | Custom NLP text | N/A (BERT analysis) | Manual sentences | Built-in to notebook |
| **Project 07** | CIFAR-10 | 10 object categories | 60,000 images | Auto via `torchvision.datasets` |
| **Project 09** | CartPole-v1 (simulated) | N/A (RL environment) | Procedurally generated | Auto via `gymnasium` |
| **Capstone** | Alam Phishing Dataset | 2 (Phishing / Legitimate) | ~11,000+ emails | Hugging Face Hub |

**Repository Size Note:** Large datasets are not stored in this repository. Standard datasets (Fashion-MNIST, CIFAR-10, CartPole) load automatically via framework APIs. See each project's README for dataset access instructions.

---

## Key Learning Outcomes

### 1. Neural Network Fundamentals
* **From Scratch:** Built forward propagation, backpropagation, and gradient descent using only NumPy.
* **Framework Mastery:** Progressed from NumPy → TensorFlow/Keras → PyTorch with deep understanding of what each layer of abstraction provides.
* **Optimization:** Adam, SGD, learning rate scheduling, dropout regularization.

### 2. Computer Vision with Deep Learning
* **CNN Design:** Convolutional layers, max pooling, feature maps, spatial hierarchies.
* **Transfer Learning:** Feature extraction and fine-tuning with ResNet50 on custom datasets.
* **Vision Transformers:** Patch-based image processing, position embeddings, attention map visualization.

### 3. Sequence Modeling & Natural Language Processing
* **RNN Family:** Understanding the vanishing gradient problem and how LSTM/GRU gating mechanisms solve it.
* **Transformers:** Self-attention, multi-head attention, positional encoding, encoder-decoder architecture.
* **BERT & Embeddings:** Bidirectional pre-training, semantic similarity, attention visualization for interpretability.

### 4. Reinforcement Learning
* **Core Framework:** Agents, environments, states, actions, rewards, and policies.
* **Q-Learning:** Bellman equation, Q-table construction, epsilon-greedy exploration.
* **RL Dynamics:** Exploration vs. exploitation, convergence analysis, reward shaping.

### 5. Multi-Agent AI Systems
* **CrewAI:** Orchestrating multiple specialized AI agents in autonomous pipelines.
* **Agentic Behavior:** Autonomous decision-making, escalation logic, and persistent memory.
* **Production Systems:** Full-stack integration (AI backend + React frontend + SQLite persistence).

---

## Tools & Frameworks

| Category | Tools Used |
|---|---|
| **Languages** | Python 3.8+ |
| **Deep Learning** | TensorFlow 2.x, Keras, PyTorch |
| **NLP & Transformers** | Hugging Face Transformers, BERT |
| **RL Environment** | OpenAI Gym / Gymnasium |
| **Multi-Agent AI** | CrewAI |
| **Data Science** | NumPy, Pandas, Matplotlib, Seaborn, Scikit-Learn |
| **Frontend** | React, Vite, Tailwind CSS |
| **Environment** | Jupyter Notebooks, Google Colab |

---

## Real-World Applications

The techniques mastered in this course are directly applicable to:

* **Cybersecurity:** Automated threat detection, phishing analysis, and multi-agent incident response (The Hunter).
* **Healthcare:** Medical image analysis with CNNs and Transformers; patient outcome prediction with sequence models.
* **Finance:** Fraud detection using ensemble classifiers; time-series forecasting with LSTMs.
* **Autonomous Systems:** Reinforcement learning for robotics navigation and control.
* **NLP Applications:** Sentiment analysis, document classification, semantic search, automated captioning.
* **Education Technology:** Interactive AI tools and explainable models for learning.

---

## Repository Structure

```text
Deep-Learning-ITAI2376/
│
├── The-Hunter-Automated-Email-Phishing-Defense-Detection-System/  # Capstone Project
│   ├── notebooks/                          # Jupyter notebooks (training, demo)
│   │   ├── The Hunter-Automated Email Phishing Defense Detection System.ipynb
│   │   └── Demo_The_Hunter_App.ipynb
│   ├── app/                                # React web application
│   ├── data/                               # Datasets and preprocessing
│   ├── models/                             # Trained model files
│   ├── results/                            # Evaluation metrics & visualizations
│   │   ├── demo_visualizations/            # Pipeline demo screenshots
│   │   └── notebook_visualizations/        # Training charts & analysis
│   ├── docs/                               # Technical documentation
│   ├── requirements.txt                    # Python dependencies
│   ├── REFLECTION.md                       # Project reflection
│   └── README.md                           # Project documentation
│
├── Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks/
│   ├── P01_A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks.pdf
│   └── README.md
│
├── Project-02-Neural-Network-Zoo/
│   ├── P02_Neural-Network-Zoo.pptx         # Full visual presentation
│   ├── P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4
│   ├── Convoshrimp/                        # Interactive web app
│   └── README.md
│
├── Project-03-Neural-Networks-from-Scratch-to-Frameworks/
│   ├── P03_Neural-Networks-from-Scratch-to-Frameworks.ipynb
│   ├── Results-&-Visualizations/           # Fashion-MNIST charts & comparisons
│   └── README.md
│
├── Project-04-Deep-Learning-for-an-11-year-old/
│   ├── P04_Deep-Learning-for-an-11-year-old.pdf
│   ├── Neural-Network-Squad/               # Interactive web app
│   └── README.md
│
├── Project-05-CNN-Puppy-or-Bagel/
│   ├── P05_CNN-Puppy-or-Bagel.ipynb
│   ├── Results-&-Visualizations/           # Confusion matrix, predictions, loss curves
│   └── README.md
│
├── Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP/
│   ├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb-Colab.pdf
│   ├── P06_Analyzing-Arrival-Through-the-Lens-of-NLP.pdf
│   ├── Results-&-Visualizations/           # Attention maps, logograms, BERT visualizations
│   └── README.md
│
├── Project-07-RNNs-vs-Transformers-vs-Vision-Transformers/
│   ├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb
│   ├── Results-&-Visualizations/           # Architecture comparisons, ViT attention maps
│   └── README.md
│
└── Project-09-Teach-an-Agent-to-Balance-a-Pole/
    ├── P09_Teach-an-Agent-to-Balance-a-Pole.ipynb
    ├── Results-&-Visualizations/           # Q-Learning training curves, reward plots
    └── README.md
```
