# Natural Language Processing Portfolio (ITAI 2373)
**Student:** Chloe Tu  
**Program:** Artificial Intelligence A.A.S  

## Course Overview
This repository serves as a comprehensive portfolio of coursework, labs, and innovative projects completed during the **ITAI 2373 Natural Language Processing** course. The work documented here demonstrates a progression from foundational text processing to advanced applications in Neural Network architecture, Generative Adversarial Networks (GANs), Voice Technology, and Ethical AI design.

## Skills & Technologies
* **Languages & Environments:** Python 3.x, Jupyter Notebooks
* **Key Libraries:** NLTK, Pandas, NumPy, Scikit-learn, TensorFlow/Keras
* **Core Competencies:**
    * **Text Preprocessing:** Tokenization, Stemming/Lemmatization, Stop-word removal, Regex cleaning.
    * **Modeling:** Artificial Neural Networks (ANNs), Seq2Seq models, Predictive Modeling.
    * **Concepts:** Vectorization (TF-IDF, Bag-of-Words), Backpropagation, Gradient Descent, GANs (Generator/Discriminator dynamics), POS Tagging.
    * **Soft Skills:** Ethical AI analysis, Technical storytelling, System design.

---

## Project & Lab Structure

### 🔹 Module 01: Introduction to NLP
* **File:** `NLP-in-Action-From-Pop-Culture-to-Processes_Chloe_Tu_ITAI_2373.pdf` (Reflective Journal)
* **Description:** An introductory exploration into the landscape of Natural Language Processing. This document analyzes how NLP is portrayed in popular culture versus its actual industrial applications, establishing a baseline understanding of AI communication capabilities.

---

### 🔹 Module 02: Text Processing and Cleaning
* **Source Code:** `Lab_02_Chloe_Tu_ITAI_2373.ipynb` (Code Implementation)
* **Documentation:** `L02_Chloe_Tu_ITAI2373.pdf` (L02-AI-History-Detecitives-PDF), `L02_Journal_Chloe_Tu_ITAI_2373.pdf` (Reflective Journal)

#### Project Details
* **Problem Statement:** Raw text data from web sources is often unstructured and noisy, containing HTML tags, special characters, and inconsistencies that hinder model performance.
* **Approach & Methodology:** Constructed a data cleaning pipeline using Python's **Regex** and **NLTK**. The process involved:
    1. Ingesting raw text data.
    2. Stripping HTML tags and non-alphanumeric characters.
    3. Normalizing text (lowercasing).
    4. Tokenizing sentences into words.
* **Results & Evaluation:** Successfully transformed a "dirty" dataset into a clean list of tokens ready for analysis.
* **Learning Outcomes:** Mastered the specific challenges of tokenization and the necessity of "data wrangling" before modeling begins.

---

### 🔹 Module 03: Audio Preprocessing (Project EchoBlade)
* **Files:** `A03_Chloe_Tu_ITAI_2373.pdf` (Technical Proposal), `L03_Chloe_Tu_ITAI2373_GameDesign.pdf` (L03-AI-Game-Master-PDF), `L03_Chloe_Tu_ITAI2373_GameDesign.docx`  (L03-AI-Game-Master-docx)
* **Description:** A creative proposal for "EchoBlade," a specialized voice recognition system designed for the MMORPG *Legends of the Shattered Realms*.
    * **Challenge:** Solving the "Cocktail Party Problem" in high-noise, reverb-heavy virtual environments.
    * **Solution:** Proposed a Seq2Seq model architecture capable of processing invented fantasy languages and utilizing dereverb algorithms to isolate player commands from background game noise.

---

### 🔹 Module 04: Introduction to Text Representation
* **Source Code:** `L04__Chloe_Tu_ITAI_2373.ipynb`  (Code Implementation)
* **Documentation:** `L04_Chloe_Tu_ITAI_2373.pdf` (L04-Explore-Generative-AI-for-Visualizling-Rendering-History-PDF) , `L04_Journal_Chloe_Tu_ITAI_2373.pdf`(Reflective Journal)

#### Project Details
* **Problem Statement:** Machine learning algorithms cannot process raw text strings; they require numerical input.
* **Approach & Methodology:** Implemented vectorization techniques to convert text into numerical features.
    * Used **Bag-of-Words (BoW)** to count word occurrences.
    * Applied **TF-IDF (Term Frequency-Inverse Document Frequency)** to weigh the importance of words relative to the corpus.
* **Results:** Generated sparse matrices representing the text data, highlighting unique vocabulary density.
* **Learning Outcomes:** Understood how to quantify word importance and the trade-offs between dense and sparse vector representations.

---

### 🔹 Module 05: Part of Speech (POS) Tagging
* **Source Code:** `L05_Tu_Chloe_ITAI2373.ipynb` (Code Implementation)
* **Documentation:** `L05_Chloe_Tu_ITAI_2373.pdf` (L05-Computational-Humor-PDF)

#### Project Details
* **Problem Statement:** To understand the syntactic structure of sentences, an AI must be able to identify the grammatical role of each word.
* **Approach & Methodology:** Utilized the **NLTK** library to build an automated tagger. The script processes sentences and assigns tags (e.g., NN for Noun, VB for Verb) based on context and definition.
* **Results:** The model successfully tagged sample sentences, enabling the identification of actions (verbs) and subjects (nouns).
* **Learning Outcomes:** Gained insight into syntactic analysis, a fundamental step for Named Entity Recognition (NER).

---

### 🔹 Module 06: Mapping the Neural Network Brain
* **Files:** `A06_AV_Chloe_Tu__ITAI_2373.pdf` (Audio/Video Walkthrough), `A06_KG_Chloe_Tu__ITAI_2373.pdf` (Knowledge Graph), `A06_RF_Chloe_Tu_ITAI 2373.pdf`(Reflection Report)
* **Description:** A conceptual visualization project that maps the biological functions of the human brain to the architectural components of Artificial Neural Networks (ANNs).
    * **Key Insight:** Mapped *Dendrites* to *Input Layers*, *Synapses* to *Weights*, and *Axons* to *Outputs*. The reflection report discusses the limitations of biological analogies when explaining supervised learning algorithms like Backpropagation.

---

### 🔹 Module 07: Sentiment and Emotion Analysis
* **Source Code:** `L07_Chloe_Tu_ITAI2373.ipynb`  (Code Implementation)
* **Documentation:** `A07_Chloe_Tu_ITAI_2373.pdf` (Reflective Journal), `L07_Chloe_Tu ITAI_2373.pdf` (L07-Neural-Networks-playground-PDF)

#### Project Details
* **Problem Statement:** Predicting user behavior (Ad-Clicks) based on historical data features.
* **Approach & Methodology:** Designed a Neural Network architecture from scratch.
    * **Architecture:** Input Layer (Time on Site, Device Type) → Hidden Layers (ReLU Activation) → Output Layer (Sigmoid Function).
    * **Training:** Implemented Forward Propagation to make predictions and Backpropagation/Gradient Descent to minimize the Loss Function.
* **Results:** The network successfully adjusted its weights to minimize error, demonstrating the mechanics of learning.
* **Learning Outcomes:** Deepened understanding of Neural Network architecture, activation functions, and the mathematics of optimization.

---

### 🔹 Module 08: Generative Adversarial Networks (Fact vs. Fiction)
* **Files:** `A08_Chloe_Tu_ITAI_2373.pdf` (Story Analysis Report), `L08_Chloe_Tu_ITAI_2373.pdf` (Lab Report)
* **Description:** A "Turing Test" style experiment designed to simulate the **Discriminator** component of a GAN. I analyzed stories generated by LLMs (Gemini, ChatGPT, Claude) against human-written events to identify patterns of authenticity.
    * **Findings:** "Real" training data relies on specific sensory details and imperfection, while "Generated" fakes often adhere to cliché narrative arcs and perfect resolution.

---

### 🔹 Module 09: Computer Vision & Image Generation
* **File:** `L09_Chloe_Tu_ITAI_2373.pdf` (Lab Report)
* **Description:** An exploration of Multimodal AI, specifically examining platforms that bridge Natural Language Processing prompts with Computer Vision to generate images. This module investigates how text embeddings are translated into visual outputs.
  
---
### 🔹 Module 10: Advanced NLP Concepts
* **File:** `L10_Chloe_Tu_ITAI2373.pdf` (Lab Report)
* **Description:** A lab report covering specialized advanced techniques in NLP, focusing on transformer architectures and deep learning applications in language tasks.

---
### 🔹 Module 11: AI Digital Assistants
* **Files:** `A11_Chloe_Tu_ITAI_2373.pdf` (Film Analysis), `L11_Chloe_Tu_ITAI_2373.pdf` (Lab Report)
* **Description:** A comparative analysis of the fictional AI "Samantha" from the movie *Her* (2013) versus modern Conversational AI agents. The report evaluates current technological limitations regarding consciousness and emotional reciprocity, while raising ethical concerns about data privacy and user dependency.

---
### 🔹 Module 12: Predictive Modeling
* **File:** `A12_Chloe_Tu_ITAI2373.pdf` (Lab Report)
* **Description:** A narrative project titled **"The Algorithmic Alibi."**
    * **Concept:** Explored the societal impact of predictive policing algorithms.
    * **Technical Focus:** Demonstrated the workflow of predictive modeling (Data Collection → Preprocessing → Training → Evaluation) and highlighted the dangers of "Automation Bias" where humans over-rely on algorithmic probability scores.

---
### 🔹 Module 13: Robotic Design & Ethical Analysis
* **File:** `A13_Chloe_Tu_ITAI_2373.pdf` (Lab Report)
* **Description:** A comprehensive design proposal for **"The Maestro,"** an autonomous entertainment robot for the hospitality industry.
    * **Framework:** Applied the "Perception-Cognition-Action" loop.
    * **Ethics:** Developed strict mitigation strategies for privacy (local-only processing) and safety (collision avoidance sensors) to adhere to core AI ethical principles.

---

## Requirements & Dependencies
To run the code provided in the `.ipynb` files, the following Python libraries are required:

```text
python>=3.8
pandas
numpy
nltk
scikit-learn
tensorflow
matplotlib
seaborn
jupyterlab
