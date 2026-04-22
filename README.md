# Chloe Tu - AI & Computer Vision Portfolio

[![GitHub](https://img.shields.io/badge/GitHub-Chloe--Tu2-181717?style=flat&logo=github&logoColor=white)](https://github.com/Chloe-Tu2)
![Data Analysis](https://img.shields.io/badge/Skill-Data_Analysis-ff69b4.svg)
![AI/ML Applied Projects](https://img.shields.io/badge/Collection-AI%2FML_Applied_Projects-blueviolet?style=flat)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-orange.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-red.svg)
![OpenCV](https://img.shields.io/badge/library-OpenCV-green.svg)
![YOLOv8](https://img.shields.io/badge/model-YOLOv8-blueviolet.svg)
![Google Colab](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## About Me
I am an **Applied AI student at Houston City College**, with a focus in **Computer Vision and Natural Language Processing**. This portfolio documents my coursework and capstone projects for **ITAI-1378: Computer Vision**, showcasing my ability to build production-ready AI systems from raw pixel manipulation to deploying state-of-the-art Visual Language Models.

---

## About This Portfolio
This portfolio was created as part of the **Applied AI and Robotics program** at **Houston City College**. It represents a collection of projects demonstrating skills in artificial intelligence, machine learning, natural language processing, and computer vision.

* **Degree Program:** Artificial Intelligence, A.A.S.
* **Institution:** Houston City College

---
## Technical Skills
* **Languages:** Python 3.8+
* **Deep Learning Frameworks:** PyTorch, TensorFlow, Keras
* **Computer Vision:** OpenCV, YOLOv8 (Ultralytics), PIL, Scikit-Image
* **Machine Learning:** Scikit-Learn, NumPy, Pandas
* **Advanced AI:** Transfer Learning, Visual Language Models (CLIP/BLIP), Transformers
* **Tools:** Jupyter Notebooks, Google Colab, Git
  
---

## Featured Projects Highlights
*Selected high-impact projects demonstrating core competencies in Object Detection, CNN Architecture, and Multi-Modal AI.*

### 1. [Workplace Safety PPE Detection System](./Computer-Vision-ITAI1378/Workplace-Safety-PPE-Detection-System)
**Focus:** Real-Time Object Detection & Safety Compliance  
**Tech:** YOLOv8, PyTorch, OpenCV  

A production-ready computer vision system designed to detect **Personal Protective Equipment (PPE)** in workplace environments.
* **Key Achievement:** Custom-trained a YOLOv8 model to detect 10 classes (Hardhats, Vests, etc.) with **77.1% mAP@50** and real-time inference speed (**66 FPS**).
* **Impact:** Enables automated safety monitoring to reduce workplace injuries.
* **View Project:** [Workplace-Safety-PPE-Detection-System](./Computer-Vision-ITAI1378/Workplace-Safety-PPE-Detection-System)

### 2. [Project 07: Custom CNN Architecture (Chihuahua vs. Muffin)](./Computer-Vision-ITAI1378/Project-07-CNN-Chihuahua-or-Muffin)
**Focus:** Deep Learning & Custom Neural Network Design  
**Tech:** PyTorch, TorchVision  

Tackled the classic "Inter-class Similarity" challenge by distinguishing between visually identical Chihuahuas and Blueberry Muffins.
* **Key Achievement:** Built a **Convolutional Neural Network (CNN)** from scratch (Conv2d, MaxPool, ReLU) that outperformed standard Dense Networks by successfully extracting spatial features like edges and textures.
* **Key Learning:** Mastered `DataLoader` implementation and analyzing Training vs. Validation loss curves to prevent overfitting.
* **View Project:** [Project-07-CNN-Chihuahua-or-Muffin](./Computer-Vision-ITAI1378/Project-07-CNN-Chihuahua-or-Muffin)

### 3. [Project 09: Visual Language Models (VLMs)](./Computer-Vision-ITAI1378/Project-09-Visual-Language-Models-(VLMs))
**Focus:** Multi-Modal AI (Vision + Text)  
**Tech:** Hugging Face Transformers, CLIP, BLIP  

Explored the frontier of AI by bridging Computer Vision with Natural Language Processing.
* **Key Achievement:** Implemented **Zero-Shot Classification** and **Semantic Image Search** (e.g., searching for "people playing sports" without tags) using OpenAI's CLIP and Salesforce's BLIP models.
* **Key Learning:** Understanding embedding spaces, contrastive learning, and automated image captioning.
* **View Project:** [Project-09-Visual-Language-Models-(VLMs)](./Computer-Vision-ITAI1378/Project-09-Visual-Language-Models-(VLMs))

---

## Course Directory (ITAI-1378)
*A progressive series of projects demonstrating the evolution from classical vision techniques to advanced AI.*

### Phase 1: Foundations of Vision
* **[Project 01: Real-World Applications of CV](./Computer-Vision-ITAI1378/Project-01-Exploring-Real-World-Applications-of-Computer-Vision)** - Research on AR & SLAM in retail/healthcare.
* **[Project 02: Image Processing Fundamentals](./Computer-Vision-ITAI1378/Project-02-Image-Processing-Fundamentals)** - Pixel manipulation, histograms, and noise reduction filters.
* **[Project 03: Image Restoration Adventure](./Computer-Vision-ITAI1378/Project-03-Image-Processing-Adventure-Quest)** - "Film Noir" mystery solving forensic clues with image processing.

### Phase 2: Feature Extraction & Classical ML
* **[Project 04: Algorithm Comparison](./Computer-Vision-ITAI1378/Project-04-Comprehensive-Feature-Extraction-&-Algorithm-Comparison)** - Benchmarking HOG, SIFT, and ORB with SVMs.
* **[Project 05: SVM Image Classification](./Computer-Vision-ITAI1378/Project-05-Focused-Image-Classification-with-SVM)** - Classifying CIFAR-10 images using Support Vector Machines.

### Phase 3: Deep Learning & Neural Networks
* **[Project 06: Intro to Neural Networks](./Computer-Vision-ITAI1378/Project-06-Neural-Networks-Chihuahua-or-Muffin)** - Solving visual tasks with Multi-Layer Perceptrons (MLP).
* **[Project 07: Convolutional Neural Networks](./Computer-Vision-ITAI1378/Project-07-CNN-Chihuahua-or-Muffin)** - *See Featured Highlights above.*

### Phase 4: Advanced Applications
* **[Project 08: Object Detection Architectures](./Computer-Vision-ITAI1378/Project-08-Object-Detection-using-Transfer-learning-and-Pascal-VOC-207-Dataset)** - Comparing Faster R-CNN, EfficientDet, and SSD.
* **[Project 09: Visual Language Models](./Computer-Vision-ITAI1378/Project-09-Visual-Language-Models-(VLMs))** - *See Featured Highlights above.*

---
## Repository Structure

```text
AI-Portfolio-Chloe-Tu/
│
├── ITAI-1378-Computer-Vision/
│   ├── Workplace-Safety-PPE-Detection-System/       # Object Detection Project
│   │   ├── notebooks/                               # Jupyter notebooks (training, evaluation, demo)
│   │   ├── models/                                  # Trained YOLOv8 models
│   │   ├── data/                                    # Dataset and samples
│   │   ├── results/                                 # Evaluation metrics & visualizations
│   │   ├── docs/                                    # Documentation & presentations
│   │   └── README.md                                # Project documentation
│   │
│   ├── Project-01-Real-World-Applications-of-CV/
│   │   ├── P01_Exploring-Real-World-Applications.pdf  # Full Research Report
│   │   └── README.md                                  # Project Documentation
│   │
│   ├── Project-02-Image-Processing-Fundamentals/
│   │   ├── P02_Image-Processing-Fundamentals.ipynb    # Main Jupyter Notebook Code
│   │   ├── P02_PF_Image-Processing-Fundamentals.pdf   # Project Report (Print Version)
│   │   ├── J02_RF_Image-Processing-Fundamentals.pdf   # Reflection Journal
│   │   ├── README.md                                  # Project Documentation
│   │   └── Results-&-Visualizations/                  # Output images and plots
│   │
│   ├── Project-03-Image-Processing-Adventure-Quest/
│   │   ├── P03_Image-Processing-Adventure-Quest.pdf   # The Case File (Full Report)
│   │   └── README.md                                  # Detective's Log (Documentation)
│   │
│   ├── Project-04-Feature-Extraction-Comparison/
│   │   ├── P04_Feature-Extraction-&-Comparison.ipynb  # Main Jupyter Notebook
│   │   ├── P04_PF_Feature-Extraction-&-Comparison.pdf # Project Report (Print Version)
│   │   ├── README.md                                  # Project Documentation
│   │   └── Results-&-Visualizations/                  # Output images and plots
│   │
│   ├── Project-05-SVM-Image-Classification/
│   │   ├── P05_SVM-with-Focused-Image-Classification.ipynb  # Main Jupyter Notebook
│   │   ├── P05_PF_SVM-with-Focused-Image-Classification.pdf # Project Report (Print Version)
│   │   ├── README.md                                        # Project Documentation
│   │   └── Results-&-Visualizations/                        # Output images and plots
│   │
│   ├── Project-06-Neural-Networks-Chihuahua-or-Muffin/
│   │   ├── P06_Neural-Networks-Chihuahua-or-Muffin.ipynb    # Main Code Notebook
│   │   ├── P06_PF_Neural-Networks-Chihuahua-or-Muffin.pdf   # Project Report (Print Version)
│   │   ├── J06_RF_Neural-Networks-Chihuahua-or-Muffin.pdf   # Reflection Journal
│   │   ├── README.md                                        # Project Documentation
│   │   └── Results-&-Visualizations/                        # Output images and plots
│   │
│   ├── Project-07-CNN-Chihuahua-or-Muffin/
│   │   ├── P07_CNN-Chihuahua-or-Muffin.ipynb        # Main PyTorch Notebook
│   │   ├── P07_PF_CNN-Chihuahua-or-Muffin.pdf       # Project Report (Print Version)
│   │   ├── J07_RF_CNN-Chihuahua-or-Muffin.pdf       # Reflection Journal
│   │   ├── README.md                                # Project Documentation
│   │   └── Results-&-Visualizations/                # Output Images and plots
│   │
│   ├── Project-08-Object-Detection-TensorFlow-PascalVOC/
│   │   ├── P08_Object-Detection-TensorFlow-VOC.ipynb        # Main Code
│   │   ├── P08_PF_Object-Detection-TensorFlow-VOC.pdf       # Project Report (Print Version)
│   │   ├── README.md                                        # Documentation
│   │   └── Results-&-Visualizations/                        # Output images and plots
│   │
│   └── Project-09-Visual-Language-Models-(VLMs)/
│       ├── P09_(VLMs)-Visual-Language-Models.ipynb  # Main Jupyter Notebook (Code)
│       ├── P09_PF_(VLMs)-Visual-Language-Models.pdf # Project Report (Print Format)
│       ├── README.md                                # Project Documentation
│       └── Results-&-Visualizations/                # Output images and plots
│
├── NLP-Natural-Language-Processing-ITAI2373/
│   ├── Module-01-Introduction-to-NLP/
│   ├── Module-02-Text-Processing-and-Cleaning/
│   ├── Module-03-Audio-Preprocessing/
│   ├── Module-04-Introduction-to-Text-Representation/
│   ├── Module-05-Part-of-Speech-Tagging/
│   ├── Module-06-Mapping-the-Neural-Network-Brain/
│   ├── Module-07-Sentiment-and-Emotion-Analysis/
│   ├── Module-08-Understanding-Generative-Adversarial-Networks-Fact-of-Fiction/
│   ├── Module-09-Exploring-Image-Generation-Platforms-in-Computer-Vision/
│   ├── Module-10-Large-Language-Models/
│   ├── Module-11-AI-Digital-Assistants/
│   ├── Module-12-Conversational-AI/
│   └── Module-13-Robotic-Design-and-Ethical-Analysis-Project/
│
├── Presentation/                                    # Final Course Presentation
└── README.md                                        # Main Portfolio Documentation
```

---

## Key Achievements
* **Production-Ready Detection:** Built a real-time PPE detection system using YOLOv8 achieving **77.1% mAP** and **66 FPS** inference speed.
* **Custom Architecture Design:** Designed and trained Convolutional Neural Networks (CNNs) from scratch in PyTorch, solving complex inter-class similarity challenges.
* **Multi-Modal AI Integration:** Implemented Visual Language Models (CLIP & BLIP) to bridge vision and text for zero-shot classification and automated captioning.
* **Research & Technical Writing:** Authored comprehensive technical reports on Augmented Reality (AR), SLAM, and Feature Extraction algorithms.

---

## Learning Journey
Through the **Applied AI and Robotics program** at Houston City College, I've moved from foundational machine learning concepts to building production-ready AI applications. My projects demonstrate:

* **Technical Depth:** Progressed from basic pixel manipulation (OpenCV) and classical features (HOG/SIFT) to complex Deep Learning architectures (CNNs, YOLO, Transformers).
* **Practical Application:** Developed real-world solutions addressing market needs in **Construction Safety** (PPE Detection) and **Digital Archiving** (Semantic Search).
* **Full-Stack Capability:** Integrated Python backends with Jupyter/Colab workflows, managing the complete pipeline from data collection to model deployment.
* **Professional Standards:** Maintained clean code, comprehensive documentation, and rigorous evaluation metrics across all projects.

---

## Contact
* **Name:** Chloe Tu
* **Program:** Applied AI & Robotics
* **Institution:** Houston City College
* **Email:** [cocobuttertutu@gmail.com]
* **LinkedIn:** [https://www.linkedin.com/in/chloe-tu-489532391/]
* **GitHub:** [https://github.com/Chloe-Tu2]

---
