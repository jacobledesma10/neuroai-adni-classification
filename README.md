# Interpretable NeuroAI for Alzheimer’s Disease Classification (ADNI)

## Project Overview

This project builds an **interpretable AI system** to classify Alzheimer’s disease stages using **multimodal data** from the Alzheimer’s Disease Neuroimaging Initiative (ADNI).  
The goal is not only high predictive performance, but **clinical transparency**—identifying which **brain regions and clinical features** most influence model decisions.

> **Mission:** Apply AI and neuroscience to create trustworthy models that support research and ultimately improve human health.

---

## Problem Statement

Alzheimer’s disease progression is heterogeneous and difficult to detect early.  
This project focuses on:

• Classifying subjects as:
  - CN (Cognitively Normal)  
  - MCI (Mild Cognitive Impairment)  
  - AD (Alzheimer’s Disease)

• Using both:
  - **MRI imaging data**
  - **Clinical + cognitive features**

• Emphasizing **interpretability** using explainable AI (XAI) methods.

---

## Dataset

**Source:** Alzheimer’s Disease Neuroimaging Initiative (ADNI)  
https://adni.loni.usc.edu

**Modalities Used**
• Structural T1-weighted MRI  
• Demographics (age, sex, education)  
• Cognitive scores (MMSE, CDR, ADAS-Cog)  
• Clinical diagnosis labels

Data access requires registration and approval from ADNI.


---

## Methods

### 1. Tabular Baseline
• Features: age, sex, education, MMSE, CDR  
• Models:
  - Logistic Regression
  - Random Forest / XGBoost

• Explainability:
  - SHAP values for feature attribution

---

### 2. MRI Model
• Preprocessing:
  - Skull stripping
  - Normalization
  - Resizing / slicing

• Model:
  - 3D CNN (or 2D CNN on axial slices)

• Output:
  - Learned image embeddings

---

### 3. Fusion Model
• Combine:
  - MRI embeddings + clinical features

• Model:
  - Multi-layer perceptron (MLP)

---

### 4. Explainable AI (XAI)

**Clinical Features**
• SHAP → feature importance

**Imaging**
• Grad-CAM → highlight brain regions influencing predictions

---

## Evaluation

Metrics:
• Accuracy  
• ROC-AUC  
• Confusion Matrix  

Validation:
• Patient-level splits (to avoid data leakage)

---

## Results

_(To be filled in as experiments complete)_

• Baseline tabular AUC: `TBD`  
• CNN MRI AUC: `TBD`  
• Fusion model AUC: `TBD`

---

## Ethics & Human-Centered AI

This project emphasizes:

• Transparency over black-box predictions  
• Bias awareness (age, sex, demographics)  
• Clinical decision *support*, not automation  
• Human oversight in all healthcare contexts  

AI should enhance—not replace—clinical judgment.

---

## Tech Stack

• Python  
• PyTorch  
• scikit-learn  
• SHAP  
• nibabel  
• OpenCV  
• matplotlib  

---

## Getting Started

```bash
git clone https://github.com/jacobledesma10/neuroai-adni-classification.git
cd neuroai-adni-classification
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
