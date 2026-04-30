# Project 05 — CNN: Puppy or Bagel?

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![Keras](https://img.shields.io/badge/framework-Keras-D00000.svg)
![ResNet50](https://img.shields.io/badge/model-ResNet50-blueviolet.svg)
![Transfer Learning](https://img.shields.io/badge/technique-Transfer_Learning-9cf.svg)
![CNN](https://img.shields.io/badge/architecture-CNN-blue.svg)
![Binary Classification](https://img.shields.io/badge/task-Binary_Classification-success.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Can You Tell the Difference?](./Results-%26-Visualizations/Puppy_or_Bagel_can_YOU_Tell.png)

This project uses a **Convolutional Neural Network (CNN)** with **Transfer Learning (ResNet50)** to tackle one of the internet's most beloved visual challenges: **Puppy or Bagel?** — distinguishing golden retriever puppies from golden sesame bagels, two subjects that are hilariously difficult to tell apart at a glance.

Beyond the fun framing, this project is a rigorous exploration of **inter-class visual similarity**, a core challenge in computer vision where classes share textures, colors, and shapes, pushing models to learn deeper discriminative features.

---

## Problem Statement

Standard image classifiers struggle when two classes share high visual similarity — the same golden-brown color, round shape, and fluffy texture. Simple feature extraction isn't enough; the model must learn **semantic structure** beyond surface-level patterns. This project asks: **Can a CNN powered by Transfer Learning reliably distinguish golden retriever puppies from golden sesame bagels, and what does it learn about each class?**

---

## Approach and Methodology

### Dataset Construction
- Curated a balanced dataset of puppy and bagel images.
- Applied data augmentation: random flips, rotations, brightness shifts, and zoom to improve generalization.
- Split into 80% training / 20% validation.

### Model Architecture: Transfer Learning with ResNet50
- **Base Model:** ResNet50 pre-trained on ImageNet (frozen during initial training).
- **Custom Head:** Global Average Pooling → Dense(256, ReLU) → Dropout(0.5) → Dense(1, Sigmoid).
- **Fine-tuning Phase:** Top layers of ResNet50 were unfrozen and trained at a reduced learning rate.

### Training Pipeline
```python
base_model = ResNet50(weights='imagenet', include_top=False, input_shape=(224, 224, 3))
base_model.trainable = False  # Feature extraction phase

model = Sequential([
    base_model,
    GlobalAveragePooling2D(),
    Dense(256, activation='relu'),
    Dropout(0.5),
    Dense(1, activation='sigmoid')
])

model.compile(optimizer=Adam(lr=1e-4), loss='binary_crossentropy', metrics=['accuracy'])
```

---

## Results and Evaluation

![Model Accuracy and Loss](./Results-%26-Visualizations/Model_accuracy_Model_loss.png)

![Model Predictions — Green = Correct, Red = Wrong](./Results-%26-Visualizations/Model_Predictions_Green_correct_Read_Wrong.png)

![Confusion Matrix — ResNet50](./Results-%26-Visualizations/Confusion_Matrix_ResNet50.png)

| Metric | Score |
|---|---|
| **Validation Accuracy** | ~90%+ |
| **Precision** | High |
| **Recall** | High |
| **Key Challenge** | Near-identical color/texture between classes |

The confusion matrix reveals the model's remaining failure modes — cases where the golden-brown color and circular shape genuinely overwhelm the semantic cues that distinguish fur from bread. These edge cases illustrate why inter-class similarity remains an open research challenge.

---

## Learning Outcomes

- Mastered the **Transfer Learning workflow**: feature extraction → fine-tuning → full training.
- Understood **ResNet50's** residual architecture and why it outperforms shallow CNNs on complex visual tasks.
- Learned to interpret **confusion matrices** and identify model failure modes.
- Gained practical experience with **data augmentation** strategies to prevent overfitting on small datasets.
- Developed intuition for **inter-class similarity** as a core computer vision challenge.

---

## Project Structure

```text
Project-05-CNN-Puppy-or-Bagel/
├── P05_CNN-Puppy-or-Bagel.ipynb                               # Main Jupyter Notebook
├── Results-&-Visualizations/                                  # Output images and plots
│   ├── Puppy_or_Bagel_can_YOU_Tell.png                        # Dataset preview — can you tell them apart?
│   ├── Puppy_or_Bagel.jpg                                     # Sample dataset image
│   ├── Model_accuracy_Model_loss.png                          # Training accuracy & loss curves
│   ├── Model_Predictions_Green_correct_Read_Wrong.png         # Prediction visualization grid
│   └── Confusion_Matrix_ResNet50.png                          # Confusion matrix
└── README.md                                                  # Project documentation (this file)
```

---

## Dependencies / Requirements

```bash
pip install tensorflow keras numpy matplotlib scikit-learn jupyter
```

**Python:** 3.8+

```
tensorflow >= 2.10
keras >= 2.10
numpy >= 1.21
matplotlib >= 3.5
scikit-learn >= 1.0
pillow >= 9.0
jupyter
```

---

## Running the Notebook

```bash
# Option 1: Local Jupyter
jupyter notebook P05_CNN-Puppy-or-Bagel.ipynb

# Option 2: Google Colab (Recommended — GPU access)
# Upload .ipynb to Google Colab → Runtime → Change runtime type → GPU → Run all
```

---

## Data Access

The dataset consists of publicly sourced images of golden retriever puppies and sesame bagels.

**Instructions:**
- Images are loaded directly in the notebook from the project's data directory.
- The notebook includes instructions to download additional samples if needed.
- **Alternative:** The [Kaggle Puppy vs. Bagel dataset](https://www.kaggle.com/datasets) can be used as a substitute — see notebook cell comments for download instructions.

**ResNet50 weights** are automatically downloaded by Keras on first run:
```python
ResNet50(weights='imagenet')  # Downloads ~100MB on first execution
```
