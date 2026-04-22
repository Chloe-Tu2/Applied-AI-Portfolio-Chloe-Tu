# ITAI-1378: Computer Vision

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-orange.svg)
![PyTorch](https://img.shields.io/badge/framework-PyTorch-red.svg)
![OpenCV](https://img.shields.io/badge/library-OpenCV-green.svg)
![YOLOv8](https://img.shields.io/badge/model-YOLOv8-blueviolet.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## Course Overview
**Institution:** Houston City College  
**Course:** ITAI-1378 Computer Vision     
**Focus:** Image Processing, CNNs & Object Detection

This course covers fundamental and advanced computer vision concepts, ranging from classical image processing and feature detection to modern deep learning architectures. The portfolio demonstrates practical proficiency in building production-ready computer vision systems, including a full-scale workplace safety detection system, custom CNNs built from scratch, and implementations of state-of-the-art Visual Language Models (VLMs).

* **Full-Scale Object Detection Project:** A complete workplace safety system using YOLOv8 (PPE Detection).
* **Comprehensive Colab Notebooks:** Detailed implementations with complete visualizations and code documentation.
* **CNN Architectures:** Models built from scratch (custom layers) and advanced Transfer Learning implementations.
* **Real-world Applications:** Image Classification & Object Detection projects with rigorous model evaluation.
* **Data Augmentation Strategies:** Techniques to improve model performance and generalization.
* **Transfer Learning:** Implementations using industry-standard backbones like VGG, ResNet, and MobileNet.
* **YOLOv8 Object Detection:** Real-time safety equipment detection with custom training pipelines.

---

## Featured Capstone Project
### [Workplace Safety PPE Detection System](./Workplace-Safety-PPE-Detection-System)
**Real-Time Object Detection for Safety Compliance**

A production-ready computer vision system designed to detect **Personal Protective Equipment (PPE)** in workplace environments. This project utilizes **YOLOv8** to identify safety gear in real-time video feeds, ensuring compliance and worker safety.

* **Technologies:** Python, YOLOv8, OpenCV, PyTorch
* **Key Features:**
    * Real-time detection of 10+ PPE classes (Hard Hats, Vests, Goggles, Gloves, etc.).
    * Custom-trained YOLOv8 model using transfer learning on a specialized dataset.
    * Comprehensive evaluation metrics (mAP, Precision, Recall) and inference visualizations.
    * Complete documentation including deployment strategy and team presentation.

---

## Project Directory
This repository contains a progressive series of projects demonstrating the evolution from classical vision techniques to advanced AI models.

### 🔹 Phase 1: Foundations of Vision
* **[Project 01:Exploring Real-World Applications of Computer Vision](./Project-01-Exploring-Real-World-Applications-of-Computer-Vision)**
    * *Focus:* Research & Analysis.
    * *Description:* An exploration of how Computer Vision powers Augmented Reality (AR) and SLAM technologies in retail and healthcare.
    * *Topics Covered:* Simultaneous Localization and Mapping (SLAM), LiDAR Depth Sensing, Edge AI Processing, Occlusion Handling, Object Tracking.
    * *Key Concepts:* Contextual awareness, geometric calibration, and the ethical implications of continuous environmental scanning.

* **[Project 02: Image Processing Fundamentals](./Project-02-Image-Processing-Fundamentals)**
    * *Focus:* Pixel Manipulation & Histograms.
    * *Description:* Deep dive into arithmetic operations, histogram equalization (improving "Mystical Meihua"), and noise reduction filters (Gaussian vs. Median).
    * *Topics Covered:* Frequency Domain Analysis (Histograms), Spatial Filtering (Convolution), Geometric Transformations (Affine), Color Space Manipulation (RGB/HSV).
    * *Advanced Techniques:* Custom Emboss Kernel design, Median vs. Gaussian blur comparison for Salt-and-Pepper noise, center-cropping rotated images.
    * *Key Libraries:* `OpenCV`, `NumPy`, `Matplotlib`.

* **[Project 03: Image Processing Adventure Quest](./Project-03-Image-Processing-Adventure-Quest)**
    * *Focus:* Creative Technical Storytelling.
    * *Description:* A "Film Noir" detective story ("The Blurred Truth") that explains complex image restoration algorithms through a narrative lens.
    * *Topics Covered:* Image Denoising, Thresholding (Binarization), Morphological Operations (Erosion/Dilation), Canny Edge Detection.
    * *Advanced Techniques:* Adaptive Thresholding for latent fingerprint recovery, Median filtering for text extraction, and Contrast Stretching for low-light evidence.
      
### 🔹 Phase 2: Feature Extraction & Classical ML
* **[Project 04: Comprehensive Feature Extraction & Algorithm Comparison](./Project-04-Comprehensive-Feature-Extraction-&-Algorithm-Comparison)**
    * *Focus:* Descriptors (HOG, SIFT, ORB).
    * *Description:* Benchmarking feature extractors and classifiers (SVM vs. Random Forest) on complex tasks like Face classification.
    * *Topics Covered:* Histogram of Oriented Gradients (HOG), Local Binary Patterns (LBP), Scale-Invariant Feature Transform (SIFT), ORB (Oriented FAST and Rotated BRIEF).
    * *Advanced Techniques:* Dimensionality reduction, comparing SVM vs. Random Forest performance, analyzing the "Texture vs. Shape" trade-off.
    * *Key Libraries:* `Scikit-Image`, `OpenCV`, `Scikit-Learn`.
   
* **[Project 05: Focused Image Classification with SVM](./Project-05-Focused-Image-Classification-with-SVM)**
    * *Focus:* Support Vector Machines.
    * *Description:* Implementing classical SVMs with rigorous preprocessing (Grayscale/Normalization) to classify CIFAR-10 images.
    * *Topics Covered:* Supervised Learning, Hyperplane Optimization, Kernel Functions (RBF/Linear).
    * *Advanced Techniques:* Grayscale conversion for dimensionality reduction, Min-Max Normalization for convergence, flattening 3D tensors into 1D feature vectors.
    * *Key Libraries:* `Scikit-Learn` (SVM), `TensorFlow` (Data Loading), `OpenCV`.
      
### 🔹 Phase 3: Deep Learning & Neural Networks
* **[Project 06: Neural Networks Chihuahua or Muffin](./Project-06-Neural-Networks-Chihuahua-or-Muffin)**
    * *Focus:* Multi-Layer Perceptrons (MLP).
    * *Description:* Solving the "Chihuahua vs. Muffin" visual challenge using dense neural networks, with extensive hyperparameter tuning experiments.
    * *Topics Covered:* Feed-Forward Networks, Activation Functions (ReLU/Sigmoid), Backpropagation, Overfitting.
    * *Advanced Techniques:* Hyperparameter Tuning (Adam vs. SGD), Dropout Regularization to prevent overfitting, comparison of Learning Rates and Network Depth.
    * *Key Libraries:* `TensorFlow`, `Keras`, `Pandas`.
      
* **[Project 07: CNN Chihuahua or Muffin](./Project-07-CNN-Chihuahua-or-Muffin)**
    * *Focus:* CNN Architecture.
    * *Description:* Building a custom CNN from scratch in PyTorch to overcome the spatial limitations of MLPs, achieving higher accuracy on the binary classification task.
    * *Topics Covered:* Convolutional Layers (Conv2d), Max Pooling, Feature Maps, Cross-Entropy Loss.
    * *Advanced Techniques:* Custom `Dataset` and `DataLoader` implementation, analyzing Training vs. Validation Loss curves to diagnose overfitting, long-term epoch stability testing.
    * *Key Libraries:* `PyTorch`, `TorchVision`.
      
### 🔹 Phase 4: Advanced Applications
* **[Project 08: Object Detection using Transfer learning and Pascal VOC 207 Dataset](./Project-08-Object-Detection-using-Transfer-learning-and-Pascal-VOC-207-Dataset)**
    * *Focus:* Faster R-CNN, EfficientDet, SSD.
    * *Description:* A comparative study of One-Stage vs. Two-Stage detectors using TensorFlow Hub on the Pascal VOC dataset.
    * *Topics Covered:* One-Stage vs. Two-Stage Detectors, Region Proposal Networks (RPN), Non-Maximum Suppression (NMS), Intersection over Union (IoU).
    * *Advanced Techniques:* Benchmarking Faster R-CNN (ResNet50) for accuracy against SSD MobileNet V2 for edge performance; visualizing confidence thresholds for overlapping objects.
    * *Key Libraries:* `TensorFlow Hub`, `TensorFlow 2.x`.
      
* **[Project 09: Visual Language Models (VLMs)](./Project-09-Visual-Language-Models-(VLMs))**
    * *Focus:* Multi-Modal AI (CLIP & BLIP).
    * *Description:* Exploring the frontier of AI with Zero-Shot Classification, Semantic Image Search, and Automated Image Captioning.
    * *Topics Covered:* Contrastive Learning (CLIP), Generative Vision-Language (BLIP), Zero-Shot Classification, Vector Embeddings.
    * *Advanced Techniques:* Semantic Image Retrieval (searching "people sports" finds relevant images without metadata), Automated Image Captioning, Visual Question Answering (VQA), computing Cosine Similarity       for embedding analysis.
    * *Key Libraries:* `Hugging Face Transformers`, `PyTorch`, `NLTK` (BLEU Score).
      
---

## Notebooks Content Overview
The Colab notebooks in this repository are designed to be comprehensive educational resources. Each notebook typically includes:

* **Well-Documented Code:** Clear markdown explanations accompanying every code block to explain the *why*, not just the *how*.
* **Executable Workflows:** End-to-end pipelines from data loading to model inference, ready to run.
* **Rich Visualizations:**
    * Training vs. Validation Loss/Accuracy curves.
    * Confusion Matrices for detailed error analysis.
    * Sample predictions with confidence scores.
* **Model Evaluation:** Deep dives into metrics (Precision, Recall, F1-Score) to assess real-world performance.
* **PDF Project Reports:** Print-friendly versions of the notebooks (prefixed with `P##_PF`), ideal for quick review without running code cells.
* **Reflection Journals:** Personal learning logs (prefixed with `J##_RF`) documenting key challenges, technical insights, and educational growth throughout each project.

---

## Datasets Used

This portfolio use a mix of industry-standard benchmarks and custom-curated datasets to solve specific vision challenges.

### Object Detection & Segmentation
* **Construction Site Safety (PPE):** A custom dataset containing 2,801 images of construction workers, annotated with 10 classes (Hardhat, Vest, Mask, etc.) for the Capstone Project.
* **Pascal VOC 2007:** The classic benchmark for object detection, used here to compare Faster R-CNN, EfficientDet, and SSD architectures.
* **MS COCO (Common Objects in Context):** A large-scale dataset used for benchmarking Visual Language Models (VLMs) in captioning and zero-shot retrieval tasks.

### Image Classification
* **CIFAR-10:** A fundamental dataset for machine learning. Used a specific subset (Ships vs. Cats) to demonstrate SVM performance on raw pixel data.
* **Chihuahua vs. Muffin:** A challenging binary classification dataset designed to test a model's ability to distinguish between visually similar classes (inter-class similarity).
* **Labeled Faces in the Wild (LFW):** Used for feature extraction benchmarking (HOG vs. SIFT) to test facial recognition algorithms.

### Note on Data Access
**Repository Size Limit:** Due to the large size of these datasets (several GBs), the raw images are **not** included directly in this GitHub repository.
* **Standard Datasets (No Download Needed):** Industry-standard datasets (CIFAR-10, Pascal VOC, COCO) are loaded directly within the notebooks using framework APIs. No manual download is required.
* *Example:* "This project uses the CIFAR-10 dataset, which can be loaded directly using `tensorflow.keras.datasets.cifar10.load_data()`".
* **Custom Datasets:** For custom data (like the PPE Project), specific download scripts or Kaggle/Roboflow instructions are provided in the respective project folder.
* **Sample Data:** Small subsets or "sample" folders are included where necessary to allow the demo notebooks to run immediately.

---

## Key Learning Outcomes

### 1. Image Processing & Enhancement
* **Preprocessing:** Normalization, resizing, and color space transformations (RGB $\leftrightarrow$ Grayscale/HSV).
* **Restoration:** Noise removal using Median/Gaussian blurs and Histogram Equalization.
* **Augmentation:** Implementation of rotation, flipping, zooming, and shifting to multiply dataset size.

### 2. Deep Learning & Architectures
* **CNN Design:** Building architectures from scratch (Conv2D, MaxPooling, BatchNormalization, Dropout).
* **Transfer Learning:** Fine-tuning pre-trained models (VGG16, ResNet50, MobileNetV2) for custom tasks.
* **Optimization:** Experimentation with Learning Rates, Optimizers (Adam vs. SGD), and Regularization (Dropout).

### 3. Object Detection & Multi-Modal AI
* **YOLOv8:** Training and deploying models for real-time inference on custom datasets.
* **Evaluation:** Analyzing Confusion Matrices, Precision, Recall, F1-Score, and mAP.
* **VLMs:** Utilizing Transformers (CLIP/BLIP) to bridge the gap between text and images.

---

## Tools & Frameworks
| Category | Tools Used |
| :--- | :--- |
| **Languages** | Python 3.8+ |
| **Deep Learning** | TensorFlow, Keras, PyTorch |
| **Computer Vision** | OpenCV (cv2), PIL, Scikit-Image, YOLOv8 (Ultralytics) |
| **Data Science** | NumPy, Pandas, Matplotlib, Seaborn, Scikit-Learn |
| **Environment** | Jupyter Notebooks, Google Colab |

---

## Real-World Applications
The techniques mastered in this course are directly applicable to:
* **Workplace Safety:** Automated PPE compliance monitoring.
* **Medical Imaging:** Disease detection from X-rays and scans.
* **Autonomous Systems:** Object detection for navigation and obstacle avoidance.
* **Digital Archiving:** Semantic search for unlabelled image databases.
* **Retail:** Automated inventory management and product recognition.

---

## Repository Structure

```text
ITAI-1378-Computer-Vision/
│
├── Workplace-Safety-PPE-Detection-System/       # Object Detection Project
│   ├── notebooks/                               # Jupyter notebooks (training, evaluation, demo)
│   ├── models/                                  # Trained YOLOv8 models
│   ├── data/                                    # Dataset and samples
│   ├── results/                                 # Evaluation metrics & visualizations
│   ├── docs/                                    # Documentation & presentations
│   └── README.md                                # Project documentation
│
├── Project-01-Real-World-Applications-of-CV/
│   ├── P01_Exploring-Real-World-Applications.pdf  # Full Research Report
│   └── README.md                                  # Project Documentation
│
├── Project-02-Image-Processing-Fundamentals/
│   ├── P02_Image-Processing-Fundamentals.ipynb    # Main Jupyter Notebook Code
│   ├── P02_PF_Image-Processing-Fundamentals.pdf   # Project Report (Print Version)
│   ├── J02_RF_Image-Processing-Fundamentals.pdf   # Reflection Journal
│   ├── README.md                                  # Project Documentation
│   └── Results-&-Visualizations/                  # Output images and plots
│
├── Project-03-Image-Processing-Adventure-Quest/
│   ├── P03_Image-Processing-Adventure-Quest.pdf   # The Case File (Full Report)
│   └── README.md                                  # Detective's Log (Documentation)
│
├── Project-04-Feature-Extraction-Comparison/
│   ├── P04_Feature-Extraction-&-Comparison.ipynb  # Main Jupyter Notebook
│   ├── P04_PF_Feature-Extraction-&-Comparison.pdf # Project Report (Print Version)
│   ├── README.md                                  # Project Documentation
│   └── Results-&-Visualizations/                  # Output images and plots
│
├── Project-05-SVM-Image-Classification/
│   ├── P05_SVM-with-Focused-Image-Classification.ipynb  # Main Jupyter Notebook
│   ├── P05_PF_SVM-with-Focused-Image-Classification.pdf # Project Report (Print Version)
│   ├── README.md                                        # Project Documentation
│   └── Results-&-Visualizations/                        # Output images and plots
│
├── Project-06-Neural-Networks-Chihuahua-or-Muffin/
│   ├── P06_Neural-Networks-Chihuahua-or-Muffin.ipynb    # Main Code Notebook
│   ├── P06_PF_Neural-Networks-Chihuahua-or-Muffin.pdf   # Project Report (Print Version)
│   ├── J06_RF_Neural-Networks-Chihuahua-or-Muffin.pdf   # Reflection Journal
│   ├── README.md                                        # Project Documentation
│   └── Results-&-Visualizations/                        # Output images and plots
│
├── Project-07-CNN-Chihuahua-or-Muffin/
│   ├── P07_CNN-Chihuahua-or-Muffin.ipynb        # Main PyTorch Notebook
│   ├── P07_PF_CNN-Chihuahua-or-Muffin.pdf       # Project Report (Print Version)
│   ├── J07_RF_CNN-Chihuahua-or-Muffin.pdf       # Reflection Journal
│   ├── README.md                                # Project Documentation
│   └── Results-&-Visualizations/                # Output Images and plots
│
├── Project-08-Object-Detection-TensorFlow-PascalVOC/
│   ├── P08_Object-Detection-TensorFlow-VOC.ipynb        # Main Code
│   ├── P08_PF_Object-Detection-TensorFlow-VOC.pdf       # Project Report (Print Version)
│   ├── README.md                                        # Documentation
│   └── Results-&-Visualizations/                        # Output images and plots
│
└── Project-09-Visual-Language-Models-(VLMs)/
    ├── P09_(VLMs)-Visual-Language-Models.ipynb  # Main Jupyter Notebook (Code)
    ├── P09_PF_(VLMs)-Visual-Language-Models.pdf # Project Report (Print Format)
    ├── README.md                                # Project Documentation
    └── Results-&-Visualizations/                # Output images and plots
```
---
