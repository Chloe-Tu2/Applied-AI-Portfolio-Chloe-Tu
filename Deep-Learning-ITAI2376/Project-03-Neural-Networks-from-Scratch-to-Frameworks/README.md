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

This project takes a ground-up approach to understanding neural networks by implementing them **from scratch using raw NumPy** — no ML libraries, no automatic differentiation, no `model.fit()` — then progressively replacing each hand-coded component with **TensorFlow/Keras equivalents**, revealing exactly what each framework does behind the scenes.

Using the **Fashion-MNIST dataset** (70,000 images across 10 clothing categories), the project compares the performance, implementation complexity, and debugging experience of a pure-NumPy neural network against a fully framework-powered model. The goal is not just to build a classifier — it is to understand neural networks well enough to build them without help.

---

## Problem Statement

Many deep learning practitioners can train a model with Keras in under 20 lines of code — but cannot explain what happens inside a forward pass, how backpropagation calculates gradients through multiple layers, why cross-entropy loss is shaped the way it is, or what `optimizer.step()` actually does to the weights.

This project confronts that gap directly: **Can we build a fully functional neural network using only NumPy, and what does that process teach us about what frameworks really do?**

---

## Approach and Methodology

### Phase 1: Neural Network from Scratch (NumPy Only)

Built every component of a multi-layer neural network without any ML library:

**Forward Propagation:**
```python
# Linear transformation
Z = np.dot(W, A_prev) + b

# ReLU activation (hidden layers)
A = np.maximum(0, Z)

# Softmax activation (output layer)
A = np.exp(Z) / np.sum(np.exp(Z), axis=0, keepdims=True)
```

**Loss Function — Cross-Entropy:**
```python
cost = -np.mean(np.sum(Y * np.log(A_output + 1e-8), axis=0))
```

**Backpropagation (Chain Rule by Hand):**
```python
# Output layer gradient
dZ_output = A_output - Y

# Hidden layer gradient (ReLU derivative)
dZ_hidden = np.dot(W_output.T, dZ_output) * (Z_hidden > 0)

# Weight updates
dW = (1/m) * np.dot(dZ, A_prev.T)
db = (1/m) * np.sum(dZ, axis=1, keepdims=True)
W -= learning_rate * dW
b -= learning_rate * db
```

**Custom Gradient Descent Optimizer:**
- Implemented SGD with manual weight and bias updates.
- No ML library functions used — pure matrix operations.
- Trained on Fashion-MNIST subset to verify correctness.

### Phase 2: Framework Implementation (TensorFlow/Keras)

Rebuilt the identical architecture in Keras Sequential API:
```python
model = Sequential([
    Flatten(input_shape=(28, 28)),
    Dense(128, activation='relu'),
    Dropout(0.2),
    Dense(64, activation='relu'),
    Dense(10, activation='softmax')
])
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(X_train, y_train, epochs=20, validation_split=0.2)
```

### Phase 3: Analysis & Comparison
- Evaluated both implementations on the full Fashion-MNIST test set.
- Compared training curves, convergence speed, and final accuracy.
- Analyzed the gap in code complexity: ~200 lines (NumPy) vs ~20 lines (Keras).

---

## Results & Visualizations

![Validation Accuracy & Loss Comparison](./Results-%26-Visualizations/Validation_accuracy_Comparison_Validation_Loss_Comparison.png)

| Metric | Scratch (NumPy) | Framework (Keras) |
|---|---|---|
| **Final Validation Accuracy** | ~85% | ~89% |
| **Training Time** | Significantly longer (CPU-only, manual loops) | Optimized (GPU-accelerated via cuDNN) |
| **Code Complexity** | ~200 lines (explicit matrix ops) | ~20 lines (high-level API) |
| **Gradient Computation** | Manual chain rule derivation | Automatic differentiation (autograd) |
| **Debugging** | Full visibility — inspect every gradient | Black-box — must use callbacks or hooks |

**Key Insight:** Keras's 4-point accuracy advantage comes from:
1. **Automatic differentiation** — no accumulated floating-point errors from manual chain rule
2. **Adam optimizer** — adaptive learning rates per parameter (vs. fixed SGD)
3. **GPU acceleration** — cuDNN-optimized tensor operations
4. **Dropout regularization** — automatically applied during training, disabled at inference

The scratch implementation reveals *exactly* what `model.fit()` does at each batch: compute forward pass → compute loss → backpropagate gradients → update weights → repeat.

---

## Learning Outcomes

- Deeply understood **forward propagation** as a series of linear transformations (matrix multiplications + bias additions) followed by element-wise nonlinear activations (ReLU, Softmax).
- Implemented **backpropagation by hand** — demystifying the chain rule, gradient flow through layers, and why the learning rate must be carefully tuned.
- Understood that frameworks like TensorFlow/Keras are abstraction layers over the exact same mathematical operations — `model.fit()` runs the same loop, just optimized.
- Gained appreciation for **automatic differentiation** — the single most impactful feature of deep learning frameworks, enabling gradients for arbitrarily complex computation graphs.
- Learned to read and compare training curves: identifying overfitting (validation loss rises while training loss falls), underfitting (both losses stay high), and successful convergence.
- Understood why even a scratch model achieving 85% on Fashion-MNIST demonstrates correct gradient flow — the same principles scale to ResNets, Transformers, and GPT-4.

---

## Project Structure

```text
Project-03-Neural-Networks-from-Scratch-to-Frameworks/
├── P03_Neural-Networks-from-Scratch-to-Frameworks.ipynb        # Main Jupyter Notebook
├── P03_Neural-Networks-from-Scratch-to-Frameworks.pdf          # PDF export of the notebook
├── Results-&-Visualizations/                                   # Output images and charts
│   ├── Fashion-MNIST_catlong.png                               # Fashion-MNIST dataset category preview
│   └── Validation_accuracy_Comparison_Validation_Loss_Comparison.png
│                                                               # Side-by-side accuracy & loss curves
└── README.md                                                   # Project documentation (this file)
```

---

## Dependencies / Requirements

```bash
pip install tensorflow numpy matplotlib jupyter
```

**Python:** 3.8+

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

**Fashion-MNIST** loads directly within the notebook — no manual download required:

```python
from tensorflow.keras.datasets import fashion_mnist
(X_train, y_train), (X_test, y_test) = fashion_mnist.load_data()
```

**Dataset Details:**
- **Images:** 70,000 grayscale images (60k train / 10k test)
- **Size:** 28×28 pixels
- **Classes:** 10 clothing categories (T-shirt, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle Boot)
- **Source:** [tensorflow.org/datasets/catalog/fashion_mnist](https://www.tensorflow.org/datasets/catalog/fashion_mnist)
