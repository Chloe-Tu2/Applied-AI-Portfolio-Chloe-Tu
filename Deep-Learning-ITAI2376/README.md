# ITAI-2376: Deep Learning

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![Keras](https://img.shields.io/badge/framework-Keras-D00000.svg)
![Hugging Face](https://img.shields.io/badge/library-Hugging_Face-yellow.svg)
![OpenAI Gym](https://img.shields.io/badge/environment-OpenAI_Gym-00BFFF.svg)
![Transformers](https://img.shields.io/badge/architecture-Transformers-9cf.svg)
![Vision Transformers](https://img.shields.io/badge/architecture-Vision_Transformers_(ViT)-blueviolet.svg)
![Diffusion Models](https://img.shields.io/badge/architecture-Diffusion_Models-ff69b4.svg)
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

This course delivers a rigorous, project-driven exploration of modern deep learning — from implementing neural networks by hand using NumPy, to deploying production-ready multi-agent AI systems. Each project builds on the last, progressively mastering more complex architectures and paradigms: CNNs for vision, Transformers for language, Vision Transformers for spatial attention, Diffusion Models for generation, Reinforcement Learning for autonomous decision-making, and finally multi-agent AI pipelines for real-world cybersecurity applications.

* **Hands-on Implementation:** Every concept is implemented in code — no black-box APIs.
* **Architecture Breadth:** RNNs → LSTMs → GRUs → Transformers → ViTs → Diffusion Models → Reinforcement Learning → Multi-Agent AI.
* **Creative Application:** Projects include NLP analysis of the film *Arrival*, a puppy-vs-bagel CNN challenge, a Heptapod alien language generator, and a custom diffusion model generating handwritten digits.
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
* Complete React-based web app interface for real-time email submission and analysis.

---

## Project Directory

### 🔹 Phase 1: Foundations & Frameworks

* **[Project 01: Comparative Analysis — ML & DL Tools](./Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks)**
    * *Focus:* Framework Survey & Decision Framework.
    * *Description:* Systematic comparison of TensorFlow, PyTorch, Keras, Scikit-Learn, JAX, and Fast.ai — evaluating ease of use, performance, deployment, and research adoption. Includes a practitioner decision framework mapping task types to optimal frameworks.
    * *Topics Covered:* Static vs. dynamic computation graphs, automatic differentiation, framework selection criteria, production vs. research trade-offs, historical evolution from Theano/Caffe to modern ecosystems.

* **[Project 02: Neural Network Zoo](./Project-02-Neural-Network-Zoo)**
    * *Focus:* Architecture Landscape & Visual Taxonomy.
    * *Description:* A comprehensive visual map of 30+ neural network architectures, themed around the Mantis Shrimp — an organism with 16 photoreceptor types, used as a metaphor for multi-modal perception. Includes a 3D rotating showcase video and the **[ConvoShrimp](./Project-02-Neural-Network-Zoo/Convoshrimp)** interactive web app.
    * *Topics Covered:* Feedforward, convolutional, recurrent, attention-based, generative, graph, and hybrid architectures. Inductive biases and architectural lineage from Perceptron through Mamba.

### 🔹 Phase 2: Building & Training Neural Networks

* **[Project 03: Neural Networks from Scratch to Frameworks](./Project-03-Neural-Networks-from-Scratch-to-Frameworks)**
    * *Focus:* Forward propagation, backpropagation, and framework internals.
    * *Description:* Built a complete neural network using only NumPy (no ML libraries), then rebuilt the same model in TensorFlow/Keras — directly comparing implementation complexity and performance on Fashion-MNIST (70,000 images, 10 clothing classes).
    * *Topics Covered:* Matrix multiplication, ReLU/Softmax activation, manual gradient computation via chain rule, Keras Sequential API, automatic differentiation. Scratch implementation (~200 lines) vs. framework implementation (~20 lines).
    * *Key Libraries:* `NumPy`, `TensorFlow`, `Keras`, `Matplotlib`.

* **[Project 04: Deep Learning for an 11-Year-Old](./Project-04-Deep-Learning-for-an-11-year-old)**
    * *Focus:* Science Communication & Educational AI.
    * *Description:* Explains all core deep learning concepts through original characters (Rex, Wally, Bella, Siggy, Tanya) and age-appropriate analogies, and brings them to life in the **[Neural-Network-Squad](./Project-04-Deep-Learning-for-an-11-year-old/Neural-Network-Squad)** interactive web application — a live, visual neural network simulator.
    * *Topics Covered:* Neurons, layers, training, loss, backpropagation, activation functions — all communicated without jargon, with directionally accurate metaphors.

### 🔹 Phase 3: Convolutional & Vision Models

* **[Project 05: CNN — Puppy or Bagel?](./Project-05-CNN-Puppy-or-Bagel)**
    * *Focus:* Transfer Learning & Inter-Class Visual Similarity.
    * *Description:* Built a ResNet50-powered CNN to tackle the internet's most delightful visual challenge: distinguishing golden retriever puppies from golden sesame bagels. A rigorous exploration of why inter-class similarity breaks naive classifiers, with full training pipeline, confusion matrix analysis, and prediction visualization.
    * *Topics Covered:* Transfer Learning (feature extraction → fine-tuning), ResNet50 residual architecture, data augmentation, confusion matrix analysis, failure-mode interpretation.
    * *Key Libraries:* `TensorFlow`, `Keras`, `NumPy`, `Matplotlib`.

### 🔹 Phase 4: Sequence Models & Transformers

* **[Project 06: Analyzing *Arrival* Through the Lens of NLP](./Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP)**
    * *Focus:* BERT, Self-Attention, Semantic Similarity & Creative AI.
    * *Description:* **Project Heptapod** — applies BERT embeddings, attention visualization, cosine similarity analysis, and a custom Heptapod logogram generator to analyze the alien language in Denis Villeneuve's *Arrival*. A creative exploration of how language structure shapes cognition (Sapir-Whorf hypothesis), modeled computationally.
    * *Topics Covered:* Bidirectional Transformers (BERT), multi-head attention, semantic embeddings, cosine similarity, temporal concept clustering in high-dimensional embedding space.
    * *Key Libraries:* `Transformers`, `PyTorch`, `Matplotlib`, `Seaborn`.

* **[Project 07: RNNs vs. Transformers vs. Vision Transformers](./Project-07-RNNs-vs-Transformers-vs-Vision-Transformers)**
    * *Focus:* Three-way architecture benchmark on CIFAR-10.
    * *Description:* A rigorous controlled experiment comparing Vanilla RNN, LSTM, GRU, Transformer, and Vision Transformer (ViT) architectures on the same task — revealing exactly why the field shifted from recurrent models to attention-based ones. Includes per-class ViT attention map visualization for deer, frog, bird, and truck.
    * *Topics Covered:* Vanishing gradients, LSTM/GRU gating mechanisms, self-attention, patch embeddings, ViT attention maps, comparative benchmarking methodology.
    * *Key Libraries:* `PyTorch`, `TorchVision`, `einops`, `Matplotlib`.

### 🔹 Phase 5: Generative Models

* **[Project 08: Diffusion Models](./Project-08-Diffusion-Models)**
    * *Focus:* DDPM — Denoising Diffusion Probabilistic Models.
    * *Description:* Implemented the full DDPM pipeline from scratch: forward noising process, U-Net denoising network conditioned on timestep, and ancestral sampling for image generation. Generated novel images (digits 0-9) and visualized the complete denoising sequence from pure noise to finished image. Compared linear vs. cosine noise schedules.
    * *Topics Covered:* Markov chains, Gaussian noise schedules, U-Net architecture, score matching, DDIM sampling, connection to Stable Diffusion.
    * *Key Libraries:* `PyTorch`, `TorchVision`, `tqdm`, `Matplotlib`.

### 🔹 Phase 6: Reinforcement Learning

* **[Project 09: Teach an Agent to Balance a Pole](./Project-09-Teach-an-Agent-to-Balance-a-Pole)**
    * *Focus:* Q-Learning, Reinforcement Learning Fundamentals.
    * *Description:* Implemented a Q-Learning agent from scratch to solve the CartPole-v1 environment — going from a random baseline (~8 steps) to a converged policy achieving 200-500+ steps through pure trial-and-error learning. Analyzed the impact of epsilon decay schedules on convergence speed.
    * *Topics Covered:* Markov Decision Processes (MDPs), Bellman equation, Q-table construction, epsilon-greedy exploration, state discretization, exploration vs. exploitation, path to DQN.
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
    * Diffusion denoising sequences (noise → image).
    * Reinforcement learning reward curves and exploration dynamics.
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
| **Project 08** | MNIST / CIFAR-10 | 10 digits / 10 objects | 70k / 60k images | Auto via `torchvision.datasets` |
| **Project 09** | CartPole-v1 (simulated) | N/A (RL environment) | Procedurally generated | Auto via `gymnasium` |
| **Capstone** | Alam Phishing Dataset | 2 (Phishing / Legitimate) | ~11,000+ emails | Hugging Face Hub |

**Repository Size Note:** Large datasets are not stored in this repository. Standard datasets (Fashion-MNIST, CIFAR-10, CartPole) load automatically via framework APIs. See each project's README for dataset access instructions.

---

## Key Learning Outcomes

### 1. Neural Network Fundamentals
* **From Scratch:** Built forward propagation, backpropagation, and gradient descent using only NumPy — no black-box APIs.
* **Framework Mastery:** Progressed from NumPy → TensorFlow/Keras → PyTorch with deep understanding of what each layer of abstraction provides.
* **Optimization:** Adam, SGD, learning rate scheduling, dropout regularization, batch normalization.

### 2. Computer Vision with Deep Learning
* **CNN Design:** Convolutional layers, max pooling, feature maps, spatial hierarchies.
* **Transfer Learning:** Feature extraction and fine-tuning with ResNet50 on custom datasets.
* **Vision Transformers:** Patch-based image processing, position embeddings, attention map visualization — what the model focuses on.

### 3. Sequence Modeling & Natural Language Processing
* **RNN Family:** The vanishing gradient problem and how LSTM/GRU gating mechanisms solve it.
* **Transformers:** Self-attention, multi-head attention, positional encoding, encoder-decoder architecture.
* **BERT & Embeddings:** Bidirectional pre-training, semantic similarity, attention visualization for interpretability.

### 4. Generative Models
* **Diffusion Models:** DDPM forward/reverse process, U-Net denoising, noise schedules, ancestral sampling.
* **Connection to Production:** Understanding the pipeline from DDPM → Latent Diffusion → Stable Diffusion.

### 5. Reinforcement Learning
* **Core Framework:** Agents, environments, states, actions, rewards, and policies.
* **Q-Learning:** Bellman equation, Q-table construction, epsilon-greedy exploration.
* **RL Dynamics:** Exploration vs. exploitation, convergence analysis, path to Deep Q-Networks.

### 6. Multi-Agent AI Systems
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
* **Creative AI:** Image generation with diffusion models; music generation with sequence models.
* **Education Technology:** Interactive AI tools and explainable models for learning (Neural-Network-Squad).

---

## Repository Structure

```text
Deep-Learning-ITAI2376/
│
├── The-Hunter-Automated-Email-Phishing-Defense-Detection-System/  # Capstone Project
│   ├── notebooks/
│   │   ├── The Hunter-Automated Email Phishing Defense Detection System.ipynb
│   │   └── Demo_The_Hunter_App.ipynb
│   ├── app/                                # React web application
│   ├── data/                               # Datasets and preprocessing
│   ├── models/                             # Trained model files
│   ├── results/
│   │   ├── demo_visualizations/            # Pipeline demo screenshots
│   │   └── notebook_visualizations/        # Training charts & analysis
│   ├── docs/                               # Technical documentation
│   ├── requirements.txt
│   ├── REFLECTION.md
│   └── README.md
│
├── Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks/
│   ├── P01_A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks.pdf
│   └── README.md
│
├── Project-02-Neural-Network-Zoo/
│   ├── P02_Neural-Network-Zoo.pptx
│   ├── P02_Neural-Network-Zoo.pdf
│   ├── P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4
│   ├── Results-&-Visualizations/           # 12 slide screenshots (01.png–12.png, 10.jpeg)
│   ├── Convoshrimp/                        # Interactive web app
│   │   ├── index.html
│   │   ├── src/
│   │   ├── public/
│   │   ├── dist/
│   │   ├── package.json
│   │   ├── vite.config.js
│   │   ├── tailwind.config.js
│   │   ├── eslint.config.js
│   │   ├── postcss.config.js
│   │   └── README.md
│   └── README.md
│
├── Project-03-Neural-Networks-from-Scratch-to-Frameworks/
│   ├── P03_Neural-Networks-from-Scratch-to-Frameworks.ipynb
│   ├── P03_Neural-Networks-from-Scratch-to-Frameworks.pdf
│   ├── Results-&-Visualizations/
│   │   ├── Fashion-MNIST_catlong.png
│   │   └── Validation_accuracy_Comparison_Validation_Loss_Comparison.png
│   └── README.md
│
├── Project-04-Deep-Learning-for-an-11-year-old/
│   ├── P04_Deep-Learning-for-an-11-year-old.pdf
│   ├── Results-&-Visualizations/           # 15 character illustration images
│   │   ├── cover-art-new.jpg
│   │   ├── 1-input-output.jpg
│   │   ├── input-output.jpg
│   │   ├── wally-weight.png
│   │   ├── bella-bias.jpg
│   │   ├── siggy-1.jpg
│   │   ├── tanya.jpg
│   │   ├── functions.jpg
│   │   ├── confused rex-1.jpg
│   │   ├── confused wally.jpg
│   │   ├── confused bella.jpg
│   │   ├── confused computer-11.jpg
│   │   ├── chaos computer scene-10.jpg
│   │   ├── rex-3.jpg
│   │   └── victory-4.jpg
│   ├── Neural-Network-Squad/               # Interactive web app
│   │   ├── index.html
│   │   ├── images/
│   │   ├── results/
│   │   ├── screenshots/
│   │   ├── CHANGELOG.md
│   │   ├── CONTRIBUTING.md
│   │   ├── LICENSE
│   │   └── README.md
│   └── README.md
│
├── Project-05-CNN-Puppy-or-Bagel/
│   ├── P05_CNN-Puppy-or-Bagel.ipynb
│   ├── P05_CNN-Puppy-or-Bagel.pdf
│   ├── Results-&-Visualizations/
│   │   ├── Puppy_or_Bagel_can_YOU_Tell.png
│   │   ├── Puppy_or_Bagel.jpg
│   │   ├── Model_accuracy_Model_loss.png
│   │   ├── Model_Predictions_Green_correct_Read_Wrong.png
│   │   └── Confusion_Matrix_ResNet50.png
│   └── README.md
│
├── Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP/
│   ├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb
│   ├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb-Colab.pdf
│   ├── P06_Analyzing-Arrival-Through-the-Lens-of-NLP.pdf
│   ├── Results-&-Visualizations/           # 11 NLP & logogram visualizations
│   │   ├── start_project_Heptapod.png
│   │   ├── Project_Heptapod_logo.png
│   │   ├── NLP_Paradigm_Comparison.png
│   │   ├── Self-Attention_Heatmap.png
│   │   ├── Circular_Attention_Visualization.png
│   │   ├── Linear_vs_Circular_Language_Visualization.png
│   │   ├── Temporal_Concepts_Similarity_In_BERT.png
│   │   ├── Heptapod_Logogram_Generator.png
│   │   ├── Louise's_Whiteboard.png
│   │   ├── Operation_First_Contact.png
│   │   └── End_of_Transmission.png
│   └── README.md
│
├── Project-07-RNNs-vs-Transformers-vs-Vision-Transformers/
│   ├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb
│   ├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.pdf
│   ├── Results-&-Visualizations/           # 12 architecture & attention map visualizations
│   │   ├── CIFAR-10_Vision_Transformers_(ViTs).png
│   │   ├── Visualize_Class_Distribution.png
│   │   ├── Three-Way_RNN_Comparison_Vanilla_RNN_vs_LSTM_Vs_GRU.png
│   │   ├── LSTM_vs_GRU_Comparison_Visualization.png
│   │   ├── Vision_Transformer_what_Does_The_Model_Focus_on.png
│   │   ├── Visualizing_ViT_Attention.png
│   │   ├── Attention_Map_For_deer.png
│   │   ├── Attention_Map_For-frog.png
│   │   ├── Attention_map_for_bird.png
│   │   ├── Attention_map_for_Truck.png
│   │   ├── Master_Comparison_Table.png
│   │   └── The_Big_Comparison_All_Architectures.png
│   └── README.md
│
├── Project-08-Diffusion-Models/
│   ├── P08_Diffusion-Models.ipynb
│   ├── P08_Diffusion-Models.pdf
│   ├── Results-&-Visualizations/           # 25 generation & training visualizations
│   │   ├── Diffusion_Model_Training_Progress.png
│   │   ├── Training_and_Validation_Loss.png
│   │   ├── Training_and_Validation_Loss_01.png
│   │   ├── Final_Training_and_Validation_Loss.png
│   │   ├──STUDENT_ACTIVITY_Generating_numbers_with_different_noise_seeds.png
│   │   ├── Smoothed_Training_and_Validation_Loss_Vali-Train_Loss_Ratio.png
│   │   ├── Final_Generated_samples.png
│   │   ├── Generated_samples_Visual_progress.png
│   │   ├── Generated_samples_Epoch 50-50.png
│   │   ├── Generated_sampls_Epoch_50-50_.png
│   │   ├── Watching_the_Generation_Process_01.png
│   │   ├── Watching_the_Generation_Process_02.png
│   │   ├── Watching_the_Generation_Process_03.png
│   │   ├── Generating_New_Images_01_Digits.png
│   │   ├── Generating_4_versions_of_number_01.png through _10.png
│   │   ├── Visualization_function_dogs.png
│   │   └── Top_1-3_Score.png
│   └── README.md
│
└── Project-09-Teach-an-Agent-to-Balance-a-Pole/
    ├── P09_Teach-an-Agent-to-Balance-a-Pole.ipynb
    ├── P09_Teach-an-Agent-to-Balance-a-Pole.pdf
    ├── Results-&-Visualizations/
    │   ├── Q-Learning-Agent-Training_Progress_On_CartPole-V1.png
    │   ├── Random_Agent-Cartpole_Scores-10-Episodes.png
    │   └── Effect_of_Exploration_Rate_Decay_On_Learning_Speed.png
    └── README.md
```
