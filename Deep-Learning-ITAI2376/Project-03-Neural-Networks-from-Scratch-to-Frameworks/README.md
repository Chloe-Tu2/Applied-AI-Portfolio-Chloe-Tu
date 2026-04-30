# Project 03 — Neural Networks from Scratch to Frameworks

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![Keras](https://img.shields.io/badge/framework-Keras-D00000.svg)
![NumPy](https://img.shields.io/badge/library-NumPy-013243.svg)
![Jupyter](https://img.shields.io/badge/tool-Jupyter-F37626.svg)
![Fashion MNIST](https://img.shields.io/badge/dataset-Fashion_MNIST-lightblue.svg)
![Classification](https://img.shields.io/badge/task-Image_Classification-success.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Fashion MNIST Dataset Preview](./Results-%26-Visualizations/Fashion-MNIST_catlong.png)

This project takes a ground-up approach to understanding neural networks by implementing them **from scratch using raw NumPy**, then progressively replacing hand-coded components with **TensorFlow/Keras equivalents** — revealing exactly what each framework does behind the scenes.

Using the **Fashion-MNIST dataset** (10 classes of clothing items), the project compares the performance and implementation complexity of a from-scratch neural network versus a fully framework-powered model, building intuition that no high-level tutorial can provide.

---

## Problem Statement

Many deep learning practitioners can train models using Keras in a few lines of code — but cannot explain what happens inside a forward pass, how backpropagation calculates gradients, or why loss functions are shaped the way they are. This project confronts that gap directly: **Can we build a fully functional neural network using only NumPy, and what does that process teach us about what frameworks really do?**

---

## Approach and Methodology

### Phase 1: Neural Network from Scratch (NumPy Only)
- Implemented **forward propagation** with manual matrix multiplications and activation functions (ReLU, Softmax).
- Implemented **backpropagation** by hand — computing gradients via the chain rule for each layer.
- Built a custom **gradient descent optimizer** without using any ML library functions.
- Trained on a subset of Fashion-MNIST to validate correctness.

### Phase 2: Framework Implementation (TensorFlow/Keras)
- Rebuilt the same architecture using Keras Sequential API.
- Compared training curves, final accuracy, and code complexity side-by-side.

### Phase 3: Analysis & Comparison
- Evaluated both implementations on the full Fashion-MNIST test set.
- Analyzed **validation accuracy** and **validation loss** across training epochs.

---

## Results and Evaluation

![Validation Accuracy & Loss Comparison](./Results-%26-Visualizations/Validation_accuracy_Comparison_Validation_Loss_Comparison.png)

| Metric | Scratch (NumPy) | Framework (Keras) |
|---|---|---|
| **Final Validation Accuracy** | ~85% | ~89% |
| **Training Time** | Significantly longer | Optimized (GPU-accelerated) |
| **Code Complexity** | ~200 lines | ~20 lines |
| **Gradient Computation** | Manual chain rule | Automatic differentiation |

Key takeaway: Keras's optimized backend (cuDNN, XLA) delivers higher accuracy with far less code, but the scratch implementation reveals *exactly* why — automatic differentiation, batch normalization under the hood, and optimized tensor operations.

---

## Learning Outcomes

- Deeply understood **forward propagation** as a series of linear transformations and nonlinear activations.
- Implemented **backpropagation by hand**, demystifying the chain rule and gradient flow.
- Understood that frameworks like TensorFlow/Keras are abstraction layers over the exact same math.
- Gained appreciation for what `model.fit()` actually does at each batch iteration.
- Learned to read and compare training curves to diagnose model behavior (overfitting, underfitting, convergence).

---

## Project Structure

```text
Project-03-Neural-Networks-from-Scratch-to-Frameworks/
├── P03_Neural-Networks-from-Scratch-to-Frameworks.ipynb       # Main Jupyter Notebook
├── Results-&-Visualizations/                                  # Output images and charts
│   ├── Fashion-MNIST_catlong.png                              # Fashion-MNIST dataset preview
│   └── Validation_accuracy_Comparison_Validation_Loss_Comparison.png
│                                                          # Training accuracy & loss curves
└── README.md                                                  # Project documentation (this file)
```

---

## Dependencies / Requirements

```bash
pip install tensorflow numpy matplotlib jupyter
```

**Python:** 3.8+  
**Key Libraries:**
```
tensorflow >= 2.10
numpy >= 1.21
matplotlib >= 3.5
jupyter
```

---

## Running the Notebook

```bash
# Option 1: Local Jupyter
jupyter notebook P03_Neural-Networks-from-Scratch-to-Frameworks.ipynb

# Option 2: Google Colab
# Upload the .ipynb file to Google Colab and run all cells
```

---

## Data Access

**Fashion-MNIST** is a standard benchmark dataset that loads directly within the notebook — no manual download required:

```python
from tensorflow.keras.datasets import fashion_mnist
(X_train, y_train), (X_test, y_test) = fashion_mnist.load_data()
```

**Dataset Details:**
- **Images:** 70,000 grayscale images (60k train / 10k test)
- **Size:** 28×28 pixels
- **Classes:** 10 clothing categories (T-shirt, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle Boot)
- **Source:** [tensorflow.org/datasets/catalog/fashion_mnist](https://www.tensorflow.org/datasets/catalog/fashion_mnist)
