# Chloe Tu — AI Portfolio

[![GitHub](https://img.shields.io/badge/GitHub-Chloe--Tu2-181717?style=flat&logo=github&logoColor=white)](https://github.com/Chloe-Tu2)
![Data Analysis](https://img.shields.io/badge/Skill-Data_Analysis-ff69b4.svg)
![AI/ML Applied Projects](https://img.shields.io/badge/Collection-AI%2FML_Applied_Projects-blueviolet?style=flat)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![pandas](https://img.shields.io/badge/library-pandas-150458.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-EE4C2C.svg)
![OpenCV](https://img.shields.io/badge/library-OpenCV-green.svg)
![YOLOv8](https://img.shields.io/badge/model-YOLOv8-blueviolet.svg)
![CrewAI](https://img.shields.io/badge/framework-CrewAI-4B0082.svg)
![Transformers](https://img.shields.io/badge/library-Hugging_Face_Transformers-yellow.svg)
![Reinforcement Learning](https://img.shields.io/badge/topic-Reinforcement_Learning-orange.svg)
![Data Curation](https://img.shields.io/badge/topic-Data_Curation-9cf.svg)
![FAIR](https://img.shields.io/badge/principle-FAIR-blueviolet.svg)
![Quality Audit](https://img.shields.io/badge/topic-Quality_Audit-orange.svg)
![Governance](https://img.shields.io/badge/topic-Governance-4B0082.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![Google Colab](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![Kaggle](https://img.shields.io/badge/platform-Kaggle-20BEFF.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

---

## About Me

I am an **Applied AI student at Houston City College**, with a focus in **Computer Vision, Deep Learning, Natural Language Processing, and Data Curation for AI**. This portfolio documents my coursework and capstone projects across the **Applied AI and Robotics program**, showcasing my ability to build production-ready AI systems — from raw pixel manipulation and multi-agent pipelines to rigorous data quality, licensing, and governance work.

---

## About This Portfolio

This portfolio was created as part of the **Applied AI and Robotics program** at **Houston City College**. It represents a collection of projects demonstrating skills in artificial intelligence, machine learning, natural language processing, computer vision, autonomous AI systems, and the curation of data as a managed asset for AI.

* **Degree Program:** Artificial Intelligence, A.A.S. Artificial Intelligence & Robotics, B.A.T.
* **Institution:** Houston City College

---

## Technical Skills

* **Languages:** Python 3.8+
* **Deep Learning Frameworks:** PyTorch, TensorFlow, Keras
* **Computer Vision:** OpenCV, YOLOv8 (Ultralytics), PIL, Scikit-Image
* **NLP & Transformers:** Hugging Face Transformers, BERT, CLIP, BLIP
* **Machine Learning:** Scikit-Learn, NumPy, Pandas
* **Data Curation & Quality:** Data sheets, quality audits, license detection, FAIR principles, governance plans, cost modeling
* **Multi-Agent AI:** CrewAI
* **Reinforcement Learning:** OpenAI Gym / Gymnasium, Q-Learning
* **Tools:** Jupyter Notebooks, Google Colab, Git, Kaggle, Excel, React, Vite

---

## Featured Projects Highlights

*Selected high-impact projects demonstrating core competencies across Computer Vision, Deep Learning, NLP, Data Curation, and Autonomous Multi-Agent AI.*

---

### 1. [The Hunter — Automated Email Phishing Defense & Detection System](./Deep-Learning-ITAI2376/The-Hunter-Automated-Email-Phishing-Defense-Detection-System)
**Focus:** Multi-Agent AI | Cybersecurity | NLP | Deep Learning  
**Tech:** CrewAI, BiLSTM, Random Forest Ensemble, React

A production-ready **multi-agent AI system** that autonomously analyzes, classifies, and responds to email phishing threats. Three specialized AI agents operate in a coordinated pipeline — scanning emails, making autonomous quarantine decisions, and tracking repeat offenders across sessions using persistent threat memory.

* **Key Achievement:** Ensemble classifier (BiLSTM + Random Forest) achieving **97%+ phishing detection accuracy** on the Alam Phishing Dataset.
* **Agentic Behavior:** Agent 2 autonomously escalates borderline cases; Agent 3 maintains cross-session repeat-offender memory — no human intervention required.
* **Impact:** A fully autonomous cybersecurity pipeline demonstrating real-world multi-agent AI deployment.
* **[View Project →](./Deep-Learning-ITAI2376/The-Hunter-Automated-Email-Phishing-Defense-Detection-System)**

---

### 2. [Workplace Safety PPE Detection System](./Computer-Vision-ITAI1378/Workplace-Safety-PPE-Detection-System)
**Focus:** Real-Time Object Detection & Safety Compliance  
**Tech:** YOLOv8, PyTorch, OpenCV

A production-ready computer vision system designed to detect **Personal Protective Equipment (PPE)** in workplace environments.

* **Key Achievement:** Custom-trained a YOLOv8 model to detect 10 classes (Hardhats, Vests, etc.) with **77.1% mAP@50** and real-time inference speed (**66 FPS**).
* **Impact:** Enables automated safety monitoring to reduce workplace injuries.
* **[View Project →](./Computer-Vision-ITAI1378/Workplace-Safety-PPE-Detection-System)**

---

### 3. [Rotten Tomatoes Curation Plan and Pilot](./Curating-Data-for-AI-Optimization-ITAI3375/Midterm-Rotten-Tomatoes-Curation-Pilot)
**Focus:** Data Curation | Quality Audit | Score Normalization | Honest Failure Reporting  
**Tech:** Python, pandas, Jupyter, Kaggle (CC0 dataset)

Full curation plan and working pilot for the Rotten Tomatoes movies + critic reviews dataset (17,712 movies, 1,130,017 reviews). The core problem: `review_score` appeared in **814 distinct string forms** and was missing in **27.1%** of reviews.

* **Key Result:** On a seeded 50,000-row sample, **72.4%** of rows survived normalization to a single 0–100 scale.
* **Honest Failure:** First letter-grade mapping agreed with the site’s own Fresh/Rotten label only **64.5%** of the time — reported as a failure, not hidden.
* **Hand Audit:** 100 records read by hand; 47 had problems.
* **[View Project →](./Curating-Data-for-AI-Optimization-ITAI3375/Midterm-Rotten-Tomatoes-Curation-Pilot)**

---

### 4. [Project 03: Neural Networks from Scratch to Frameworks](./Deep-Learning-ITAI2376/Project-03-Neural-Networks-from-Scratch-to-Frameworks)
**Focus:** Neural Network Fundamentals | Backpropagation | Framework Internals  
**Tech:** NumPy (scratch), TensorFlow, Keras, Fashion-MNIST

Built a complete multi-layer neural network using **only NumPy** — forward propagation, backpropagation via chain rule, and gradient descent, all hand-coded — then rebuilt the identical architecture in TensorFlow/Keras to reveal exactly what frameworks do behind the scenes.

* **Key Achievement:** Scratch implementation (~200 lines of NumPy) achieving ~85% accuracy on Fashion-MNIST, vs Keras (~20 lines) at ~89% — making the framework abstraction cost/benefit concrete and measurable.
* **Key Learning:** Deeply understood automatic differentiation, the role of `model.fit()` at each batch, and why frameworks like Keras outperform manual implementations.
* **[View Project →](./Deep-Learning-ITAI2376/Project-03-Neural-Networks-from-Scratch-to-Frameworks)**

---

### 5. [Project 07: RNNs vs. Transformers vs. Vision Transformers](./Deep-Learning-ITAI2376/Project-07-RNNs-vs-Transformers-vs-Vision-Transformers)
**Focus:** Architecture Benchmark | Sequence Models | Vision AI  
**Tech:** PyTorch, einops, CIFAR-10

A rigorous three-way benchmark comparing RNN/LSTM/GRU, Transformers, and Vision Transformers (ViT) on CIFAR-10 — with full attention map visualization revealing what each model "sees."

* **Key Achievement:** Demonstrated ViT achieving 75%+ accuracy with interpretable attention maps showing semantic focus regions for deer, frog, bird, and truck.
* **Key Learning:** Understood the architectural shift from sequential to attention-based models through a controlled experiment.
* **[View Project →](./Deep-Learning-ITAI2376/Project-07-RNNs-vs-Transformers-vs-Vision-Transformers)**

---

### 6. [Project 06: Analyzing *Arrival* Through the Lens of NLP](./Deep-Learning-ITAI2376/Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP)
**Focus:** BERT | NLP | Semantic Similarity | Creative AI  
**Tech:** Hugging Face Transformers, BERT, PyTorch

**Project Heptapod** — applies BERT embeddings, self-attention visualization, cosine similarity analysis, and a custom Heptapod logogram generator to analyze the alien language in Denis Villeneuve's *Arrival*. A creative exploration of how language structure shapes cognition, modeled computationally.

* **Key Achievement:** Extracted and visualized BERT multi-head attention weights; generated circular alien logograms encoding meaning radially rather than sequentially.
* **Key Learning:** Connected the Sapir-Whorf hypothesis to computational NLP — BERT's embedding geometry reflects linear human time perception, not Heptapod B's circular structure.
* **[View Project →](./Deep-Learning-ITAI2376/Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP)**

---

### 7. [Project 09: Visual Language Models (VLMs)](./Computer-Vision-ITAI1378/Project-09-Visual-Language-Models-(VLMs))
**Focus:** Multi-Modal AI (Vision + Text)  
**Tech:** Hugging Face Transformers, CLIP, BLIP

Explored the frontier of AI by bridging Computer Vision with Natural Language Processing — zero-shot classification, semantic image search, and automated captioning.

* **Key Achievement:** Implemented Zero-Shot Classification and Semantic Image Search (searching "people playing sports" without metadata tags) using CLIP and BLIP.
* **[View Project →](./Computer-Vision-ITAI1378/Project-09-Visual-Language-Models-(VLMs))**

---

## Course Directory

---

### [Deep Learning — ITAI-2376](./Deep-Learning-ITAI2376)
*A progressive series of projects from neural network fundamentals to production multi-agent AI.*

#### Phase 1: Foundations & Frameworks
* **[Project 01: ML & DL Tools Comparison](./Deep-Learning-ITAI2376/Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks)** — Framework survey & decision framework: TensorFlow vs. PyTorch vs. Keras vs. JAX.
* **[Project 02: Neural Network Zoo](./Deep-Learning-ITAI2376/Project-02-Neural-Network-Zoo)** — Visual taxonomy of 30+ architectures + Mantis Shrimp 3D showcase + [ConvoShrimp interactive app](./Deep-Learning-ITAI2376/Project-02-Neural-Network-Zoo/Convoshrimp).

#### Phase 2: Building & Training Neural Networks
* **[Project 03: Neural Networks from Scratch to Frameworks](./Deep-Learning-ITAI2376/Project-03-Neural-Networks-from-Scratch-to-Frameworks)** — Built a neural network using only NumPy, then rebuilt it in TensorFlow/Keras on Fashion-MNIST.
* **[Project 04: Deep Learning for an 11-Year-Old](./Deep-Learning-ITAI2376/Project-04-Deep-Learning-for-an-11-year-old)** — Science communication + the [Neural-Network-Squad interactive app](./Deep-Learning-ITAI2376/Project-04-Deep-Learning-for-an-11-year-old/Neural-Network-Squad).

#### Phase 3: Convolutional & Vision Models
* **[Project 05: CNN — Puppy or Bagel?](./Deep-Learning-ITAI2376/Project-05-CNN-Puppy-or-Bagel)** — ResNet50 transfer learning for inter-class visual similarity (golden puppies vs. golden bagels).

#### Phase 4: Sequence Models & Transformers
* **[Project 06: Analyzing *Arrival* Through the Lens of NLP](./Deep-Learning-ITAI2376/Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP)** — Project Heptapod: BERT embeddings + alien logogram generator + attention visualization. *(See Featured Highlights above.)*
* **[Project 07: RNNs vs. Transformers vs. Vision Transformers](./Deep-Learning-ITAI2376/Project-07-RNNs-vs-Transformers-vs-Vision-Transformers)** — Three-way architecture benchmark on CIFAR-10 with ViT attention maps. *(See Featured Highlights above.)*

#### Phase 5: Generative Models
* **[Project 08: Diffusion Models](./Deep-Learning-ITAI2376/Project-08-Diffusion-Models)** — Full DDPM implementation from scratch: forward noising process, U-Net denoiser, and image generation from pure noise.

#### Phase 6: Reinforcement Learning
* **[Project 09: Teach an Agent to Balance a Pole](./Deep-Learning-ITAI2376/Project-09-Teach-an-Agent-to-Balance-a-Pole)** — Q-Learning agent solving CartPole-v1 from complete ignorance (~8 steps) to 200-500+ step mastery.

#### Capstone
* **[The Hunter — Multi-Agent Phishing Defense System](./Deep-Learning-ITAI2376/The-Hunter-Automated-Email-Phishing-Defense-Detection-System)** — Production multi-agent AI for cybersecurity. *(See Featured Highlights above.)*

---

### [Computer Vision — ITAI-1378](./Computer-Vision-ITAI1378)
*A progressive series of projects demonstrating the evolution from classical vision techniques to advanced AI models.*

#### Phase 1: Foundations of Vision
* **[Project 01: Real-World Applications of CV](./Computer-Vision-ITAI1378/Project-01-Exploring-Real-World-Applications-of-Computer-Vision)** — Research on AR & SLAM in retail/healthcare.
* **[Project 02: Image Processing Fundamentals](./Computer-Vision-ITAI1378/Project-02-Image-Processing-Fundamentals)** — Pixel manipulation, histograms, and noise reduction filters.
* **[Project 03: Image Restoration Adventure](./Computer-Vision-ITAI1378/Project-03-Image-Processing-Adventure-Quest)** — "Film Noir" mystery solving forensic clues with image processing.

#### Phase 2: Feature Extraction & Classical ML
* **[Project 04: Algorithm Comparison](./Computer-Vision-ITAI1378/Project-04-Comprehensive-Feature-Extraction-&-Algorithm-Comparison)** — Benchmarking HOG, SIFT, and ORB with SVMs.
* **[Project 05: SVM Image Classification](./Computer-Vision-ITAI1378/Project-05-Focused-Image-Classification-with-SVM)** — Classifying CIFAR-10 images using Support Vector Machines.

#### Phase 3: Deep Learning & Neural Networks
* **[Project 06: Intro to Neural Networks](./Computer-Vision-ITAI1378/Project-06-Neural-Networks-Chihuahua-or-Muffin)** — Solving visual tasks with Multi-Layer Perceptrons (MLP).
* **[Project 07: Convolutional Neural Networks](./Computer-Vision-ITAI1378/Project-07-CNN-Chihuahua-or-Muffin)** — Custom CNN in PyTorch for the Chihuahua vs. Muffin challenge.

#### Phase 4: Advanced Applications
* **[Project 08: Object Detection Architectures](./Computer-Vision-ITAI1378/Project-08-Object-Detection-using-Transfer-learning-and-Pascal-VOC-207-Dataset)** — Comparing Faster R-CNN, EfficientDet, and SSD.
* **[Project 09: Visual Language Models](./Computer-Vision-ITAI1378/Project-09-Visual-Language-Models-(VLMs))** — CLIP & BLIP for zero-shot classification and semantic search. *(See Featured Highlights above.)*

#### Capstone
* **[Workplace Safety PPE Detection System](./Computer-Vision-ITAI1378/Workplace-Safety-PPE-Detection-System)** — Real-time YOLOv8 PPE detection. *(See Featured Highlights above.)*

---

### [NLP — ITAI-2373](./NLP-Natural-Language-Processing-ITAI2373)
*13-module progression through Natural Language Processing — from text cleaning to Generative AI.*

* Module 01-02: NLP Foundations & Text Processing
* Module 03: Audio Preprocessing
* Module 04: Text Representation (TF-IDF, Word Embeddings)
* Module 05: Part-of-Speech Tagging
* Module 06: Neural Network Brain Mapping
* Module 07: Sentiment & Emotion Analysis
* Module 08: Generative Adversarial Networks (Fact or Fiction)
* Module 09: Image Generation Platforms
* Module 10: Large Language Models
* Module 11-12: AI Digital Assistants & Conversational AI
* Module 13: Robotic Design & Ethical Analysis Project

---

### [Curating Data for A.I. Optimization — ITAI-3375](./Curating-Data-for-AI-Optimization-ITAI3375)
*Data as a managed asset: lifecycle, quality, licensing, governance, valuation, and the practical work of making data usable and defensible for AI systems.*

#### Foundations
* **[Project 01: Curation in Your Industry](./Curating-Data-for-AI-Optimization-ITAI3375/Project-01-Curation-in-Your-Industry)** — Mapped curation work inside Meta’s algorithmic content engineering organization
* **[Project 02: Profile the Job Market](./Curating-Data-for-AI-Optimization-ITAI3375/Project-02-Profile-the-Job-Market-You-Are-Entering)** — Labor-market analysis of data curation and AI data roles
* **[Project 03: The FAIR and Open Memo](./Curating-Data-for-AI-Optimization-ITAI3375/Project-03-The-FAIR-and-Open-Memo)** — Policy memo applying FAIR and Open principles

#### Quality, Licensing & Documentation
* **[Project 04: Assess a Public Dataset as a Business Asset](./Curating-Data-for-AI-Optimization-ITAI3375/Project-04-Assess-a-Public-Dataset-as-a-Business-Asset)** — Valuation and risk assessment of a public dataset
* **[Project 05: License Detective](./Curating-Data-for-AI-Optimization-ITAI3375/Project-05-License-Detective)** — Systematic license identification and downstream-use implications
* **[Project 06: Compare Three Repositories](./Curating-Data-for-AI-Optimization-ITAI3375/Project-06-Compare-Three-Repositories-for-One-Task)** — Side-by-side evaluation of three data repositories
* **[Project 07: Build a Complete Data Sheet](./Curating-Data-for-AI-Optimization-ITAI3375/Project-07-Build-a-Complete-Data-Sheet)** — Full data sheet following established documentation standards
* **[Project 08: Run a Full Quality Audit](./Curating-Data-for-AI-Optimization-ITAI3375/Project-08-Run-a-Full-Quality-Audit)** — End-to-end quality audit (Spotify + YouTube dataset) with quantified missingness

#### Pipelines & Knowledge Work
* **[Project 09: Build a Small Extraction Pipeline](./Curating-Data-for-AI-Optimization-ITAI3375/Project-09-Build-a-Small-Extraction-Pipeline)** — Working extraction pipeline (notebook + CSV)
* **[Project 10: Audit an Instruction/Preference Dataset](./Curating-Data-for-AI-Optimization-ITAI3375/Project-10-Audit-an-Instruction-or-Preference-Dataset)** — Structured audit of alignment-style data
* **[Project 11: Build and Evaluate a Small Knowledge Base](./Curating-Data-for-AI-Optimization-ITAI3375/Project-11-Build-and-Evaluate-a-Small-Knowledge-Base)** — Construction and evaluation of a retrieval knowledge base
* **[Project 12: Design a Labeling Pipeline](./Curating-Data-for-AI-Optimization-ITAI3375/Project-12-Design-a-Labeling-Pipeline)** — End-to-end labeling design (includes Excel specification)
* **[Project 13: Generate and Evaluate a Synthetic Dataset](./Curating-Data-for-AI-Optimization-ITAI3375/Project-13-Generate-and-Evaluate-a-Synthetic-Dataset)** — Synthetic data generation + quality evaluation

#### Governance, Cost & Business
* **[Project 14: Build a Governance and Compliance Plan](./Curating-Data-for-AI-Optimization-ITAI3375/Project-14-Build-a-Governance-and-Compliance-Plan)** — Governance and compliance plan for AI data assets
* **[Project 15: The Budget Reduction Memo](./Curating-Data-for-AI-Optimization-ITAI3375/Project-15-The-Budget-Reduction-Memo)** — Decision memo under budget pressure
* **[Project 16: Build a Cost Model and Business Case](./Curating-Data-for-AI-Optimization-ITAI3375/Project-16-Build-a-Cost-Model-and-Business-Case)** — Quantitative cost model (Excel) + business case

#### Midterm
* **[Rotten Tomatoes Curation Plan and Pilot](./Curating-Data-for-AI-Optimization-ITAI3375/Midterm-Rotten-Tomatoes-Curation-Pilot)** — Full plan + working pilot; 72.4% survival after score normalization; honest failure reporting on letter-grade mapping *(See Featured Highlights above.)*

---

## Repository Structure

```text
AI-Portfolio-Chloe-Tu/
│
├── Deep-Learning-ITAI2376/
│   ├── The-Hunter-Automated-Email-Phishing-Defense-Detection-System/  # Capstone
│   │   ├── notebooks/                    # Training & demo notebooks
│   │   ├── app/                          # React web application
│   │   ├── data/                         # Datasets
│   │   ├── models/                       # Trained model files
│   │   ├── results/
│   │   │   ├── demo_visualizations/      # Pipeline screenshots
│   │   │   └── notebook_visualizations/  # Training charts
│   │   ├── docs/                         # Documentation
│   │   ├── requirements.txt
│   │   └── README.md
│   │
│   ├── Project-01-A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks/
│   │   ├── P01_A-Comparative-Analysis-of-Machine-Learning-and-Deep-Learning-Tools-and-Frameworks.pdf
│   │   └── README.md
│   │
│   ├── Project-02-Neural-Network-Zoo/
│   │   ├── P02_Neural-Network-Zoo.pptx
│   │   ├── P02_Neural-Network-Zoo.pdf
│   │   ├── P02_Neural-Network-Zoo-Mantis-Shrimp-D-Rotational-Video-Showcase.mp4
│   │   ├── Results-&-Visualizations/     # 12 slide screenshots
│   │   ├── Convoshrimp/                  # Interactive web app
│   │   └── README.md
│   │
│   ├── Project-03-Neural-Networks-from-Scratch-to-Frameworks/
│   │   ├── P03_Neural-Networks-from-Scratch-to-Frameworks.ipynb
│   │   ├── P03_Neural-Networks-from-Scratch-to-Frameworks.pdf
│   │   ├── Results-&-Visualizations/     # Fashion-MNIST & loss curves
│   │   └── README.md
│   │
│   ├── Project-04-Deep-Learning-for-an-11-year-old/
│   │   ├── P04_Deep-Learning-for-an-11-year-old.pdf
│   │   ├── Results-&-Visualizations/     # 15 character illustrations
│   │   ├── Neural-Network-Squad/         # Interactive web app
│   │   └── README.md
│   │
│   ├── Project-05-CNN-Puppy-or-Bagel/
│   │   ├── P05_CNN-Puppy-or-Bagel.ipynb
│   │   ├── P05_CNN-Puppy-or-Bagel.pdf
│   │   ├── Results-&-Visualizations/     # Confusion matrix, predictions, loss curves
│   │   └── README.md
│   │
│   ├── Project-06-Analyzing-Arrival-Through-the-Lens-of-NLP/
│   │   ├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb
│   │   ├── P06_ARRIVAL_HEPTAPOD_LAB.ipynb-Colab.pdf
│   │   ├── P06_Analyzing-Arrival-Through-the-Lens-of-NLP.pdf
│   │   ├── Results-&-Visualizations/     # 11 attention maps & logograms
│   │   └── README.md
│   │
│   ├── Project-07-RNNs-vs-Transformers-vs-Vision-Transformers/
│   │   ├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.ipynb
│   │   ├── P07_RNNs-vs-Transformers-vs-Vision-Transformers.pdf
│   │   ├── Results-&-Visualizations/     # 12 visualizations incl. deer/frog/bird/truck attention maps
│   │   └── README.md
│   │
│   ├── Project-08-Diffusion-Models/
│   │   ├── P08_Diffusion-Models.ipynb
│   │   ├── P08_Diffusion-Models.pdf
│   │   ├── Results-&-Visualizations/     # 25 generation & training visualizations
│   │   └── README.md
│   │
│   └── Project-09-Teach-an-Agent-to-Balance-a-Pole/
│       ├── P09_Teach-an-Agent-to-Balance-a-Pole.ipynb
│       ├── P09_Teach-an-Agent-to-Balance-a-Pole.pdf
│       ├── Results-&-Visualizations/     # Q-Learning training curves & epsilon decay
│       └── README.md
│
├── Computer-Vision-ITAI1378/
│   ├── Workplace-Safety-PPE-Detection-System/       # Capstone — Object Detection
│   │   ├── notebooks/                               # Jupyter notebooks
│   │   ├── models/                                  # Trained YOLOv8 models
│   │   ├── data/                                    # Dataset and samples
│   │   ├── results/                                 # Evaluation metrics & visualizations
│   │   ├── docs/                                    # Documentation & presentations
│   │   └── README.md
│   │
│   ├── Project-01-Exploring-Real-World-Applications-of-Computer-Vision/
│   ├── Project-02-Image-Processing-Fundamentals/
│   ├── Project-03-Image-Processing-Adventure-Quest/
│   ├── Project-04-Comprehensive-Feature-Extraction-&-Algorithm-Comparison/
│   ├── Project-05-Focused-Image-Classification-with-SVM/
│   ├── Project-06-Neural-Networks-Chihuahua-or-Muffin/
│   ├── Project-07-CNN-Chihuahua-or-Muffin/
│   ├── Project-08-Object-Detection-using-Transfer-learning-and-Pascal-VOC-207-Dataset/
│   └── Project-09-Visual-Language-Models-(VLMs)/
│
├── NLP-Natural-Language-Processing-ITAI2373/
│   ├── Module-01 through Module-13/
│   └── README.md
│  
├── Curating-Data-for-AI-Optimization-ITAI3375/
│   ├── README.md
│   ├── Midterm-Rotten-Tomatoes-Curation-Pilot/
│   │   ├── README.md
│   │   ├── Midterm_Project_Curation_Plan_and_Pilot_Chloe_Kaire_ITAI_3375.pdf
│   │   ├── Midterm_Presentation_ITAI3375.pdf
│   │   └── Rotten_tomatoes_pilot_ITAI_3375.ipynb
│   ├── Project-01-Curation-in-Your-Industry/
│   ├── Project-02-Profile-the-Job-Market-You-Are-Entering/
│   ├── Project-03-The-FAIR-and-Open-Memo/
│   ├── Project-04-Assess-a-Public-Dataset-as-a-Business-Asset/
│   ├── Project-05-License-Detective/
│   ├── Project-06-Compare-Three-Repositories-for-One-Task/
│   ├── Project-07-Build-a-Complete-Data-Sheet/
│   ├── Project-08-Run-a-Full-Quality-Audit/
│   ├── Project-09-Build-a-Small-Extraction-Pipeline/
│   ├── Project-10-Audit-an-Instruction-or-Preference-Dataset/
│   ├── Project-11-Build-and-Evaluate-a-Small-Knowledge-Base/
│   ├── Project-12-Design-a-Labeling-Pipeline/
│   ├── Project-13-Generate-and-Evaluate-a-Synthetic-Dataset/
│   ├── Project-14-Build-a-Governance-and-Compliance-Plan/
│   ├── Project-15-The-Budget-Reduction-Memo/
│   └── Project-16-Build-a-Cost-Model-and-Business-Case/
│
├── Presentation/                                    # Final Portfolio Presentation
│   ├── visualizations/                              # Images used in presentation
│   │   ├── Portfolio_Overview.html                  # HTML portfolio overview page
│   │   ├── Portfolio_Slideshow.html                 # HTML slideshow presentation
│   │   ├── hunter_interface.png                     # The Hunter web app screenshot
│   │   └── val_batch0_pred.jpg                      # PPE detection output sample
│   ├── README.md                                    # 5-slide portfolio presentation (Markdown)
│   ├── NLP-Natural-Language-Processing-ITAI2373-Portfolio-summary.txt
│   ├── Pf_ChloeT_Portfolio_Summary_ITAI_2376.md     # Portfolio summary document
│   └── Pf_Chloe_Tu_Portfolio_Summary_ITAI_2376.pdf  # Portfolio summary (PDF submission)
│
└── README.md                                        # This file
```

---

## Key Achievements

* **Multi-Agent AI Pipeline:** Built The Hunter — a fully autonomous phishing detection system with three CrewAI agents achieving **97%+ accuracy**, autonomous escalation, and cross-session threat memory.
* **Production-Ready Detection:** Built a real-time PPE detection system using YOLOv8 achieving **77.1% mAP** and **66 FPS** inference speed.
* **Data Curation Judgment:** Designed and piloted a full curation plan for Rotten Tomatoes critic scores (814 formats → single 0–100 scale); reported a 64.5% letter-grade mapping failure instead of hiding it; hand-audited 100 records (47 problems found).
* **Custom Architecture Design:** Implemented neural networks from scratch in NumPy, and designed CNNs, RNNs, LSTMs, and Vision Transformers in PyTorch/TensorFlow.
* **Multi-Modal AI Integration:** Implemented Visual Language Models (CLIP & BLIP) to bridge vision and text for zero-shot classification and automated captioning.
* **Reinforcement Learning:** Trained a Q-Learning agent from random baseline to 200-500+ step CartPole mastery through pure trial-and-error.
* **Governance & Business Case:** Produced data sheets, quality audits, license reviews, governance plans, and a quantitative cost model — treating data as a managed asset, not a free input.
* **Science Communication:** Created an 11-year-old-accessible deep learning explanation and interactive Neural-Network-Squad web app.
* **Research & Technical Writing:** Authored comprehensive technical reports on ML/DL frameworks, neural network architecture taxonomies, and NLP paradigm comparisons.

---

## Learning Journey

Through the **Applied AI and Robotics program** at Houston City College, I've progressed from foundational machine learning concepts to building production-ready, autonomous AI applications and treating data as a first-class asset:

* **Technical Depth:** Progressed from pixel manipulation (OpenCV) and classical features (HOG/SIFT) → deep learning architectures (CNNs, YOLO, Transformers, ViTs) → multi-agent autonomous AI systems (CrewAI).
* **Data as an Asset:** Learned to profile, audit, license-check, document, and govern datasets so they are defensible and usable for AI — including quantified quality failures and honest reporting of what did not work.
* **Practical Application:** Developed real-world solutions addressing market needs in **Construction Safety** (PPE Detection), **Cybersecurity** (The Hunter), **Digital Archiving** (Semantic Search), **Reinforcement Learning** (autonomous control), and **Data Governance**.
* **Full-Stack Capability:** Integrated Python backends with Jupyter/Colab workflows, React frontends, and SQLite persistence — managing the complete pipeline from data collection to model deployment.
* **Professional Standards:** Maintained clean code, comprehensive documentation, and rigorous evaluation metrics across all projects.

---

## Contact

* **Name:** Chloe Tu
* **Program:** Applied AI & Robotics
* **Institution:** Houston City College
* **Email:** [tuchloe2@gmail.com](mailto:tuchloe2@gmail.com)
* **LinkedIn:** [https://www.linkedin.com/in/chloe-tu-019a453bb/](https://www.linkedin.com/in/chloe-tu-019a453bb/)
* **GitHub:** [github.com/Chloe-Tu2](https://github.com/Chloe-Tu2)

---
