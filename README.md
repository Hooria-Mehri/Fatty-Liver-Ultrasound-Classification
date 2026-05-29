# Fatty Liver Ultrasound Image Classification (Advanced Pattern Recognition)

This repository contains the official implementation for the advanced Pattern Recognition course project directed by **Dr. Shalbaf**. The project focuses on the automated assessment and grading of nonalcoholic fatty liver disease (NAFLD) using clinical B-mode ultrasound images.

## Project Overview & Objectives
The main goal is to evaluate and compare classical machine learning workflows (Radiomics feature extraction) against deep transfer learning paradigms for a 3-class liver steatosis grading task:
* **Class 0:** Mild / Healthy (Fat infiltration < 33%)
* **Class 1:** Moderate (Fat infiltration 34% - 66%)
* **Class 2:** Advanced / Severe (Fat infiltration > 67%)

The dataset originates from ultrasound scans of 55 patients (550 B-mode images) pre-evaluated via liver biopsies adhering to the NASH Clinical Research Network scoring system.

---

## Technical Pipeline

### 1. Image Enhancement & Preprocessing
* Applied **Global and Local Statistical Enhancement** techniques to normalize image contrast and improve liver-kidney boundary visibility.
* Utilized spatial domain filters (**Laplacian and Gaussian masks**) and frequency domain processing for micro-structure clarity.
* Boundary extraction via morphological operations and edge-detection algorithms.

### 2. Radiomics Feature Extraction
* Extracted first-order and second-order texture statistics using the `pyradiomics` library in Python.
* Generated multi-directional spatial matrices (0°, 45°, 90°) across 1, 2, and 3-step neighborhoods.
* Normalized features and exported the final dataset into a structured CSV format.

### 3. Classification Models & Deep Learning
* **Deep Transfer Learning:** Implemented a fine-tuned convolutional neural network architecture based on **EfficientNet** for automated feature learning, optimizing the final layers to break through the limits of classical classification.
* **Machine Learning Baselines:** Evaluated and compared performance metrics across multiple classifiers, including **Random Forest (RF)** and **Support Vector Machines (SVM)**.
* **Class Imbalance Mitigation:** Integrated strategic data augmentation to address class prevalence issues during the training/validation phase.

---

## Repository Contents
* 📁 `pattern.ipynb` - Complete Python source code including data augmentation, feature extraction, model training, and evaluation matrices.
* 📄 `hooriamehri-pattern.pdf` - Comprehensive final project report compiling all experimental results, statistical charts, confusion matrices, and detailed analytical findings.
* 📄 `LICENSE` - MIT License protecting the software implementation.

## Evaluation Metrics
Models are fully evaluated and documented in the final report based on:
* Accuracy, Precision, Recall, F1-Score, and Area Under the ROC Curve (AUC).
