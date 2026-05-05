# Portfolio Presentation — Chloe Tu
## Applied AI & Robotics | Houston City College | A.A.S. Artificial Intelligence

> **Presentation Format:** Portfolio Summary · 5 Slides  
> **GitHub:** [github.com/Chloe-Tu2](https://github.com/Chloe-Tu2)  
> **File:** `Pf_ChloeT_Portfolio_Summary_ITAI_2376`

---

---

# SLIDE 1 — Introduction

## Chloe Tu
### Applied AI & Robotics Student — Houston City College

**Degree Program:** Artificial Intelligence, A.A.S.

---

### AI Specialization & Interests

> *"Building production-ready AI systems — from handcrafted neural networks to multi-agent autonomous pipelines — with a focus on Computer Vision, Deep Learning, and Natural Language Processing."*

**Core Interests:**
- **Computer Vision** — Real-time object detection, CNNs, Vision Transformers
- **Deep Learning** — Neural architectures from scratch to production deployment
- **NLP & Transformers** — BERT, semantic analysis, multi-modal AI
- **Autonomous AI Agents** — Multi-agent pipelines with persistent memory

---

### GitHub Portfolio (Live)

## [github.com/Chloe-Tu2](https://github.com/Chloe-Tu2)

---

### Contact

| | |
|---|---|
| Email | tuchloe2@gmail.com |
| LinkedIn | [linkedin.com/in/chloe-tu-019a453bb](https://www.linkedin.com/in/chloe-tu-019a453bb/) |
| GitHub | [github.com/Chloe-Tu2](https://github.com/Chloe-Tu2) |
| Institution | Houston City College |

---

---

# SLIDE 2 — Learning Journey

## From Pixels to Autonomous Agents

```
YEAR 1 ──────────────────────────────────────────────────────► NOW

 ITAI-1378                ITAI-2373                ITAI-2376
 ┌──────────────┐         ┌────────────────┐        ┌──────────────────┐
 │   COMPUTER   │ ──────► │    NATURAL     │ ──────►│      DEEP        │
 │    VISION    │         │   LANGUAGE     │        │    LEARNING      │
 └──────────────┘         │  PROCESSING    │        └──────────────────┘
                          └────────────────┘
 • OpenCV / PIL           • NLTK, Regex               • NumPy → PyTorch
 • HOG · SIFT · ORB       • TF-IDF · BoW              • CNNs · ViTs · BERT
 • SVMs · MLPs            • POS Tagging               • DDPM Diffusion
 • Custom CNNs            • Neural Nets               • Q-Learning RL
 • Transfer Learning      • GANs (Fact/Fiction)       • CrewAI Agents
 • YOLOv8 Real-Time       • Ethical AI Design         • 97%+ Accuracy
   77.1% mAP@50 · 66 FPS   Seq2Seq · LLMs              Multi-Agent Pipeline
```

---

### Key Milestones Timeline

| Phase | Course | Key Achievement |
|---|---|---|
| **Foundations** | ITAI-1378 CV | Classical vision → deep CNNs → PPE YOLOv8 (77.1% mAP, 66 FPS) |
| **Language AI** | ITAI-2373 NLP | Text processing → TF-IDF → GANs → Ethical AI Robotics design |
| **Deep Learning** | ITAI-2376 DL | NumPy scratch net → ViTs → Diffusion Models → 3-Agent Phishing System |

---

### Technologies Mastered

```
Languages:       Python 3.8+
Frameworks:      PyTorch · TensorFlow/Keras · Hugging Face Transformers
Vision:          OpenCV · YOLOv8 (Ultralytics) · PIL · Scikit-Image
NLP/AI:          BERT · CLIP · BLIP · NLTK · CrewAI
ML/Science:      NumPy · Pandas · Scikit-Learn · Matplotlib · Seaborn
RL:              OpenAI Gymnasium
Full-Stack:      React · Vite · SQLite
Tools:           Jupyter · Google Colab · Git
```

---

### Growth Trajectory

```
Complexity
    |
 ** |                                              **** The Hunter
 ** |                                         **** (Multi-Agent AI)
 ** |                                    **** Diffusion Models / ViTs
 ** |                               **** BERT & Transformers
 ** |                          **** YOLOv8 / Transfer Learning
 ** |                     **** Custom CNNs
 ** |                **** SVMs / Feature Extraction
 ** |           **** Image Processing
 ** |      **** Python Fundamentals
    +──────────────────────────────────────────────► Time
        CV Start   NLP Start    DL Start        Now
```

---

---

# SLIDE 3 — Featured Projects

## Three Most Significant Projects

---

## PROJECT 1: The Hunter — Automated Email Phishing Defense & Detection System

**Course:** ITAI-2376 Deep Learning | **Type:** Capstone Final Project  
**GitHub:** [View Project](../Deep-Learning-ITAI2376/The-Hunter-Automated-Email-Phishing-Defense-Detection-System)

> *A production-ready multi-agent AI system that autonomously analyzes, classifies, escalates, and tracks email phishing threats — with no human intervention required.*

**Key Technologies:** `CrewAI` · `BiLSTM` · `Random Forest` · `PyTorch` · `React` · `SQLite`

---

### Architecture — Three-Agent Autonomous Pipeline

```
 Incoming Email
       |
       v
 ┌─────────────────────────────────────────────────────────────────────┐
 │  AGENT 1 — The Analyst (Email Scanner & Feature Extractor)          │
 │  • Reads raw headers, body text, sender domain, URL patterns        │
 │  • Extracts 15+ features: URL count, keyword flags, domain age      │
 │  • Output: structured feature vector → Agent 2                      │
 └──────────────────────────────────┬──────────────────────────────────┘
                                    |
                                    v
 ┌─────────────────────────────────────────────────────────────────────┐
 │  AGENT 2 — The Arbiter (Autonomous Classifier & Escalation Engine)  │
 │  • Runs BiLSTM neural network + Random Forest Ensemble              │
 │  • Score >= 0.85  → Auto-quarantine (no human needed)               │
 │  • Score 0.50–0.84 → Autonomously escalates to human review         │
 │  • Score < 0.50   → Clears to inbox                                 │
 │  • Full decision rationale logged with confidence score             │
 └──────────────────────────────────┬──────────────────────────────────┘
                                    |
                                    v
 ┌─────────────────────────────────────────────────────────────────────┐
 │  AGENT 3 — The Archivist (Repeat Offender Memory & Threat Intel)    │
 │  • Persistent SQLite database of flagged senders (cross-session)    │
 │  • Recognizes repeat offenders even after program restarts          │
 │  • Auto-elevates threat level for known-bad domains                 │
 │  • Generates structured threat intelligence reports                 │
 └─────────────────────────────────────────────────────────────────────┘
                                    |
                                    v
 React Web Dashboard — Real-time analyst review interface
```

---

### Results & Performance

| Metric | Score |
|---|---|
| **Detection Accuracy (Ensemble)** | **97%+** |
| Precision | 96.8% |
| Recall | 97.4% |
| F1-Score | 97.1% |
| Autonomous Quarantine Rate | 89% of threats — no human review |
| Cross-Session Memory | 100% repeat-offender recognition |

---

### Technical Stack

| Component | Technology | Role |
|---|---|---|
| Agent Framework | CrewAI | Orchestrates 3-agent autonomous pipeline |
| Primary Classifier | BiLSTM (PyTorch) | Sequential pattern recognition in email text |
| Ensemble Model | Random Forest (Scikit-learn) | Structured feature-based detection |
| Ensemble Strategy | Weighted voting | BiLSTM + RF for maximum robustness |
| Persistence | SQLite | Cross-session repeat-offender memory |
| Web Interface | React + Vite | Real-time analyst dashboard |
| Training Data | Alam Phishing Dataset | 18,000+ labeled emails |

---

## PROJECT 2: Workplace Safety PPE Detection System

**Course:** ITAI-1378 Computer Vision | **Type:** Capstone Final Project  
**GitHub:** [View Project](../Computer-Vision-ITAI1378/Workplace-Safety-PPE-Detection-System)

> *A real-time computer vision system detecting Personal Protective Equipment on live camera feeds — achieving 66 FPS inference at 77.1% mAP.*

**Key Technologies:** `YOLOv8` · `PyTorch` · `OpenCV` · `Google Colab GPU`

---

### Architecture — Detection Pipeline

```
 Camera Feed (Live Video / Image)
          |
          v
 ┌────────────────────────────────────────────┐
 │  PREPROCESSING                             │
 │  • Frame normalization → 640x640           │
 │  • Mosaic augmentation (training)          │
 │  • Color jitter · flip · scale transforms  │
 └────────────────────┬───────────────────────┘
                      |
                      v
 ┌────────────────────────────────────────────┐
 │  YOLOv8 CUSTOM-TRAINED MODEL               │
 │  • Backbone: CSPDarknet with C2f modules   │
 │  • Head: Decoupled detection head          │
 │  • Transfer learning from COCO weights     │
 │  • 100 epochs · batch 16 · img 640x640     │
 └────────────────────┬───────────────────────┘
                      |
                      v
 ┌────────────────────────────────────────────┐
 │  10-CLASS DETECTION OUTPUT                 │
 │  [+] Hardhat        [-] No-Hardhat         │
 │  [+] Safety Vest    [-] No-Safety-Vest     │
 │  [+] Gloves         [-] No-Gloves          │
 │  [+] Safety Boots   [-] No-Safety-Boots    │
 │  [P] Person (worker)   [M] Machinery       │
 └────────────────────────────────────────────┘
          |
          v
 Compliance Alert — flags violations in real-time
```

---

### Results & Performance

| Metric | Score |
|---|---|
| **mAP@50 (Primary)** | **77.1%** |
| mAP@50:95 | 48.3% |
| **Inference Speed** | **66 FPS** (real-time GPU) |
| Precision | 80.2% |
| Recall | 72.6% |
| Classes Detected | 10 PPE categories |
| Training Epochs | 100 |

---

## PROJECT 3: RNNs vs. Transformers vs. Vision Transformers (ViT)

**Course:** ITAI-2376 Deep Learning | **Type:** Project 07  
**GitHub:** [View Project](../Deep-Learning-ITAI2376/Project-07-RNNs-vs-Transformers-vs-Vision-Transformers)

> *A rigorous three-way benchmark on CIFAR-10 with full ViT attention map visualization — showing exactly why the field shifted from recurrent to attention-based models.*

**Key Technologies:** `PyTorch` · `einops` · `CIFAR-10` · `Matplotlib`

---

### Architecture Comparison

```
 CIFAR-10 Dataset (60,000 images · 10 classes)
           |
    ┌──────┴──────┬───────────────┐
    v             v               v
 ┌──────┐    ┌──────────┐   ┌───────────────────┐
 │ RNN  │    │Transformer│   │ Vision Transformer │
 │ LSTM │    │(Self-Attn)│   │      (ViT)         │
 │  GRU │    │           │   │  Patch Embeddings  │
 └──────┘    └──────────┘   └───────────────────┘
    |              |                  |
    v              v                  v
 Vanishing      Parallel         Spatial Attention
 Gradients      Attention        Maps per Class:
 Sequential     Global           Deer · Frog
 Processing     Context          Bird · Truck
    |              |                  |
    └──────────────┴──────────────────┘
                   |
                   v
          75%+ ViT Accuracy on CIFAR-10
         + Interpretable Attention Maps
```

---

---

# SLIDE 4 — Skills & Competencies

## Technical Skills Overview

### Core AI Competencies

| Domain | Technologies | Proficiency |
|---|---|---|
| **Deep Learning** | PyTorch · TensorFlow · Keras | ██████████ Advanced |
| **Computer Vision** | OpenCV · YOLOv8 · CNNs · ViTs | █████████░ Advanced |
| **NLP & Transformers** | BERT · Hugging Face · NLTK · CLIP | ████████░░ Proficient |
| **Generative AI** | Diffusion Models (DDPM) · GANs | ███████░░░ Proficient |
| **Reinforcement Learning** | Q-Learning · Gymnasium · CartPole | ███████░░░ Proficient |
| **Multi-Agent AI** | CrewAI · Autonomous Pipelines | ████████░░ Proficient |
| **Full-Stack AI** | React · SQLite · Vite · Python APIs | ███████░░░ Proficient |

---

### Architecture Breadth — Implemented From Scratch

```
BUILT FROM SCRATCH (NumPy / Pure Code):
  • MLP (NumPy only — forward prop, backprop, gradient descent)
  • CNN (custom Conv2D, MaxPool, feature maps — PyTorch)
  • LSTM · GRU · BiLSTM (gating mechanisms, vanishing gradient solutions)
  • Transformer (self-attention, multi-head attention, positional encoding)
  • Vision Transformer / ViT (patch embeddings, attention map visualization)
  • DDPM Diffusion Model (U-Net denoiser, forward noising, ancestral sampling)
  • Q-Learning Agent (Bellman equation, Q-table, epsilon-greedy exploration)

DEPLOYED IN PRODUCTION CONTEXT:
  • YOLOv8 (real-time PPE Detection — 66 FPS · 10 classes)
  • CrewAI Multi-Agent Pipeline (The Hunter — 97%+ accuracy)
  • React + SQLite Web Application (full-stack AI dashboard)
```

---

### All Projects At-a-Glance

#### ITAI-2376: Deep Learning (9 Projects + Capstone)

| Project | Focus | Key Tech | Highlight |
|---|---|---|---|
| P01 | ML/DL Framework Comparison | TF · PyTorch · JAX | Decision framework for 6 frameworks |
| P02 | Neural Network Zoo | React · Vite | Visual taxonomy of 30+ architectures + 3D Mantis Shrimp video |
| P03 | Neural Net from Scratch | NumPy · TF/Keras | ~200-line scratch net vs 20-line Keras on Fashion-MNIST |
| P04 | Deep Learning for 11-year-olds | React Web App | 5 original characters + Neural-Network-Squad interactive app |
| P05 | CNN Puppy or Bagel? | ResNet50 · TF | Transfer learning on inter-class visual similarity challenge |
| P06 | Arrival NLP (Project Heptapod) | BERT · Transformers | Alien logogram generator + BERT attention visualization |
| P07 | RNNs vs ViTs Benchmark | PyTorch · einops | 3-way CIFAR-10 benchmark + ViT attention maps |
| P08 | Diffusion Models | PyTorch · U-Net | Full DDPM: noise → image generation pipeline |
| P09 | Teach Agent to Balance Pole | Gymnasium | Q-Learning: 8 steps → 200-500+ step CartPole mastery |
| **Capstone** | **The Hunter** | **CrewAI · BiLSTM** | **3-agent phishing defense, 97%+ accuracy** |

#### ITAI-1378: Computer Vision (9 Projects + Capstone)

| Project | Focus | Key Tech | Highlight |
|---|---|---|---|
| P01 | Real-World CV Applications | Research | AR & SLAM in retail/healthcare |
| P02 | Image Processing Fundamentals | OpenCV · NumPy | Histogram equalization, Gaussian/Median noise filters |
| P03 | Adventure Quest (Film Noir) | OpenCV | Forensic image restoration via narrative storytelling |
| P04 | Feature Extraction & Comparison | HOG · SIFT · ORB | SVM vs Random Forest face classification benchmark |
| P05 | SVM Image Classification | Scikit-Learn | CIFAR-10 classification with kernel SVM |
| P06 | Neural Networks Chihuahua/Muffin | TF · Keras | MLP with Adam/SGD hyperparameter experiments |
| P07 | CNN Chihuahua/Muffin | PyTorch | Custom CNN from scratch: Conv2d → MaxPool → Dense |
| P08 | Object Detection Architectures | TF Hub | Faster R-CNN vs EfficientDet vs SSD on Pascal VOC |
| P09 | Visual Language Models (VLMs) | CLIP · BLIP | Zero-shot classification + semantic image search |
| **Capstone** | **PPE Detection System** | **YOLOv8 · PyTorch** | **77.1% mAP · 66 FPS real-time · 10 classes** |

#### ITAI-2373: Natural Language Processing (13 Modules)

| Module | Focus | Highlight |
|---|---|---|
| M01 | Intro to NLP | NLP in pop culture vs real industrial applications |
| M02 | Text Processing & Cleaning | NLTK + Regex cleaning pipeline (AI History Detectives) |
| M03 | Audio Preprocessing | "EchoBlade" Seq2Seq voice system for MMORPGs |
| M04 | Text Representation | Bag-of-Words vs TF-IDF vectorization |
| M05 | POS Tagging | NLTK auto-tagger for syntactic analysis |
| M06 | Neural Network Brain Mapping | Brain anatomy → ANN architecture knowledge graph |
| M07 | Sentiment & Emotion Analysis | Neural net predicting ad-clicks from behavioral data |
| M08 | GANs — Fact or Fiction | Turing Test: Human vs LLM-generated story detection |
| M09 | Image Generation Platforms | Text-to-image: NLP embeddings → visual outputs |
| M10 | Large Language Models | Transformer architecture deep dive |
| M11 | AI Digital Assistants | "Her" (2013) vs modern conversational AI ethics analysis |
| M12 | Predictive Modeling | "The Algorithmic Alibi" — automation bias in policing |
| M13 | Robotic Design & Ethics | "The Maestro" autonomous hospitality robot proposal |

---

### Soft Skills

| Skill | Demonstrated In |
|---|---|
| **Science Communication** | Explained deep learning to an 11-year-old (written + interactive web app) |
| **Technical Writing** | Comprehensive READMEs, lab reports, and PDFs for every project |
| **Research Methodology** | Controlled benchmark design for RNN vs Transformer vs ViT study |
| **Full-Stack Integration** | Python AI backends + React frontends + SQLite persistence |
| **Ethical AI Reasoning** | Automation bias analysis, privacy frameworks, robotic ethics proposals |
| **Creative Storytelling** | Film noir image processing, alien language NLP, narrative-driven labs |

---

---

# SLIDE 5 — Reflection & Next Steps

## What I Learned

> *"Every project in this program pushed me past what I thought I could build. Starting from manually computing gradients through NumPy matrices, to watching three AI agents coordinate autonomously to catch phishing emails — the growth was exponential and the learning was real. The PPE project showed me that computer vision can save lives. The Hunter showed me that AI agents can operate as true autonomous systems."*

---

### Key Reflections

**Real-World Impact (PPE Detection)**  
Building the PPE detection system connected AI theory directly to human safety. Achieving 66 FPS real-time inference meant the system could actually work on a live construction site — not just in a notebook.

**Autonomous Systems (The Hunter)**  
The most important lesson from the capstone: understanding what separates a *model* from a *system*. Agent 2's escalation logic and Agent 3's persistent memory transformed a classifier into a truly autonomous pipeline.

**Depth Over Breadth**  
Implementing neural networks from scratch (P03 — NumPy only) gave me intuition no tutorial could provide. I now understand what frameworks actually do at every abstraction layer.

**Language & Ethics (ITAI-2373)**  
NLP is not just text processing — it is the interface between human cognition and machine reasoning. Studying Automation Bias and ethical AI robotics design has fundamentally shaped how I think about building responsible systems.

**Creativity Amplifies Learning**  
Projects like Project Heptapod (alien language via BERT), the Film Noir image restoration, and the Neural-Network-Squad app proved that creative framing makes technical material more rigorous, not less.

---

### Future Learning Goals

| Goal | Why |
|---|---|
| **Deep Q-Networks (DQN)** | Extend Q-Learning to neural function approximation for complex RL environments |
| **Stable Diffusion Fine-Tuning** | Build on DDPM foundation toward conditional domain-specific image generation |
| **Multi-Modal Agents** | Combine The Hunter's agent pipeline with vision + NLP tools for richer threat analysis |
| **Cloud Deployment (AWS/GCP)** | Deploy AI systems with full CI/CD pipelines for production-ready delivery |
| **LLM Fine-Tuning** | Fine-tune open-source LLMs for cybersecurity and workplace safety domains |

---

### Professional Contact

| | |
|---|---|
| **Name** | Chloe Tu |
| **Program** | Applied AI & Robotics, A.A.S. |
| **Institution** | Houston City College |
| **Email** | tuchloe2@gmail.com |
| **LinkedIn** | [linkedin.com/in/chloe-tu-019a453bb](https://www.linkedin.com/in/chloe-tu-019a453bb/) |
| **GitHub** | [github.com/Chloe-Tu2](https://github.com/Chloe-Tu2) |

---

> *"This portfolio represents my professional identity in AI. Every project is something I'm proud to show a recruiter today — and a foundation I'll keep building on. The Hunter and the PPE system are not just coursework; they are proof that I can build AI that works in the real world."*

---

**File:** `PRESENTATION_README.md`  
**Companion PDF:** `Pf_Chloe_Tu_Portfolio_Summary_ITAI_2376.pdf`  
**GitHub:** [github.com/Chloe-Tu2](https://github.com/Chloe-Tu2)
