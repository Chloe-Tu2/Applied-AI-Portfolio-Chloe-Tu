# Project 05 — CNN: Puppy or Bagel?

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow-FF6F00.svg)
![Keras](https://img.shields.io/badge/framework-Keras-D00000.svg)
![ResNet50](https://img.shields.io/badge/model-ResNet50-blueviolet.svg)
![Transfer Learning](https://img.shields.io/badge/technique-Transfer_Learning-9cf.svg)
![CNN](https://img.shields.io/badge/architecture-CNN-blue.svg)
![Binary Classification](https://img.shields.io/badge/task-Binary_Classification-success.svg)
![Data Augmentation](https://img.shields.io/badge/technique-Data_Augmentation-orange.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Can You Tell the Difference?](./Results-%26-Visualizations/Puppy_or_Bagel_can_YOU_Tell.png)

This project uses a **Convolutional Neural Network (CNN)** with **Transfer Learning (ResNet50)** to tackle one of the internet's most beloved visual challenges: **Puppy or Bagel?** — distinguishing golden retriever puppies from golden sesame bagels, two subjects that are hilariously difficult to tell apart at a glance.

Beyond the fun framing, this project is a rigorous exploration of **inter-class visual similarity** — a core challenge in computer vision where two classes share the same textures, colors, and shapes (golden-brown, round, fluffy), pushing models to learn deeper semantic structure rather than surface-level visual patterns.

The project follows a full production-style deep learning workflow: dataset curation, data augmentation, transfer learning in two phases (feature extraction → fine-tuning), evaluation with confusion matrices, and failure-mode analysis.

---

## Problem Statement

Standard image classifiers struggle when two classes share high visual similarity. In the puppy-vs-bagel challenge, the network cannot distinguish based on color (both golden-brown), shape (both round), or texture (both roughly fluffy/bumpy). The model must learn **semantic structure** — what is a living creature vs. a baked good — from the visual features it can observe.

This project asks: **Can a CNN powered by Transfer Learning reliably distinguish golden retriever puppies from golden sesame bagels, and what do its failure modes reveal about how the model represents each class?**

---

## Approach and Methodology

### Dataset Construction
- Curated a balanced dataset of puppy and bagel images, ensuring class balance.
- Applied data augmentation to prevent overfitting on the small dataset:
  - Random horizontal flips
  - Random rotations (±15°)
  - Brightness/contrast shifts
  - Random zoom (±10%)
- Split: 80% training / 20% validation.

### Model Architecture: Transfer Learning with ResNet50

**Why ResNet50?**
ResNet50 is pre-trained on ImageNet (1.2M images, 1000 classes) and has already learned rich visual representations: edges, textures, object parts, and semantic structures. Transfer learning allows us to repurpose these learned features for a new binary classification task.

```python
base_model = ResNet50(weights='imagenet', include_top=False, input_shape=(224, 224, 3))
base_model.trainable = False  # Phase 1: freeze all ResNet layers

model = Sequential([
    base_model,
    GlobalAveragePooling2D(),
    Dense(256, activation='relu'),
    Dropout(0.5),
    Dense(1, activation='sigmoid')
])

model.compile(optimizer=Adam(lr=1e-4), loss='binary_crossentropy', metrics=['accuracy'])
```

**Training Pipeline — Two Phases:**

| Phase | ResNet Layers | Learning Rate | Purpose |
|---|---|---|---|
| **Phase 1: Feature Extraction** | Frozen (no updates) | 1e-4 | Train only the custom classification head |
| **Phase 2: Fine-Tuning** | Top layers unfrozen | 1e-5 | Adapt ResNet's high-level features to puppies/bagels |

Fine-tuning at a reduced learning rate prevents the pre-trained weights from being destroyed by large gradient updates.

---

## Results & Visualizations

![Puppy or Bagel — Dataset Sample](./Results-%26-Visualizations/Puppy_or_Bagel.jpg)

![Model Accuracy and Loss Curves](./Results-%26-Visualizations/Model_accuracy_Model_loss.png)

![Model Predictions — Green = Correct, Red = Wrong](./Results-%26-Visualizations/Model_Predictions_Green_correct_Read_Wrong.png)

![Confusion Matrix — ResNet50](./Results-%26-Visualizations/Confusion_Matrix_ResNet50.png)

| Metric | Score |
|---|---|
| **Validation Accuracy** | ~90%+ |
| **Precision** | High — few false positives |
| **Recall** | High — few missed detections |
| **Primary Failure Mode** | Edge cases with extreme color/texture similarity |

### Analysis of Failure Cases
The confusion matrix reveals the model's remaining failure modes: cases where the golden-brown color and circular shape genuinely overwhelm the semantic cues that distinguish fur from bread. These edge cases — a bagel with a fluffy texture, or a puppy curled into a perfect circle — illustrate why inter-class similarity remains an open computer vision research challenge.

The model's errors are *interesting* errors: they occur on precisely the images that would fool human observers too.

---

## Learning Outcomes

- Mastered the full **Transfer Learning workflow**: feature extraction → fine-tuning → evaluation, and understood *why* two separate phases are needed.
- Understood **ResNet50's residual architecture** — how skip connections allow gradient flow through 50+ layers, solving the vanishing gradient problem that plagued deep CNNs.
- Learned to interpret **confusion matrices** as a diagnostic tool: identifying not just accuracy, but *where* and *why* the model fails.
- Gained practical experience with **data augmentation** strategies to prevent overfitting on small, curated datasets.
- Developed intuition for **inter-class similarity** as a fundamental computer vision challenge — and why semantic understanding (not just texture matching) is what separates good models from great ones.
- Understood why ResNet's ImageNet-learned features transfer successfully: edges → textures → object parts → semantic concepts form a hierarchy applicable across visual domains.

---

## Project Structure

```text
Project-05-CNN-Puppy-or-Bagel/
├── P05_CNN-Puppy-or-Bagel.ipynb                               # Main Jupyter Notebook
├── P05_CNN-Puppy-or-Bagel.pdf                                  # PDF export of the notebook
├── Results-&-Visualizations/
│   ├── Puppy_or_Bagel_can_YOU_Tell.png                        # Dataset preview — can you tell them apart?
│   ├── Puppy_or_Bagel.jpg                                     # Sample dataset image
│   ├── Model_accuracy_Model_loss.png                          # Training accuracy & loss curves
│   ├── Model_Predictions_Green_correct_Read_Wrong.png         # Prediction visualization grid
│   └── Confusion_Matrix_ResNet50.png                          # Confusion matrix
└── README.md
```

---

## Dependencies / Requirements

```bash
pip install tensorflow keras numpy matplotlib scikit-learn pillow jupyter
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

- Images are loaded directly in the notebook from the project's data directory.
- **Alternative:** The [Kaggle Puppy vs. Bagel dataset](https://www.kaggle.com/datasets) can be used as a substitute.

**ResNet50 weights** are automatically downloaded by Keras on first run (~100MB):
```python
ResNet50(weights='imagenet')  # Downloads automatically from Keras/TF model hub
```
