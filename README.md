# Plant Pathology 2020 – Apple Leaf Disease Detection & Farmer Web App

This project builds a deep learning model to detect foliar diseases in apple leaves using the **Plant Pathology 2020** dataset and exposes it through a simple **web application for farmers**.  
The goal is to support faster, more accurate disease diagnosis and reduce misuse of agrochemicals.

---

## 🔍 Problem Statement

Manual diagnosis of apple leaf diseases by human experts is:

- Time-consuming and expensive  
- Prone to misdiagnosis, especially under varying **light**, **angle**, **age of leaf**, and **overlapping symptoms**  
- Directly linked to **overuse/misuse of chemicals**, resistant pathogen strains, and economic loss

This project uses computer vision to:

1. Classify a leaf image as **healthy** or **diseased**
2. Distinguish between **multiple disease types**, including cases where **more than one disease appears on a single leaf**
3. Handle **rare classes** and **novel symptoms** as far as the dataset allows
4. Be robust to **different camera conditions** (angle, light, shade, leaf age)
5. Provide an interface that **farmers can actually use** via a website

---

## 🎯 Objectives

- Train a deep learning model on the **Plant Pathology 2020** dataset to classify apple leaf images.
- Support **multi-class / multi-label disease prediction** (depending on dataset labels and formulation).
- Optimize model performance using **mean column-wise ROC AUC**, the competition’s evaluation metric.
- Build a **user-friendly web interface** where farmers can:
  - Upload or capture a leaf image
  - Get predicted disease probabilities
  - See simple guidance text (e.g., “Likely healthy”, “Possible rust”, etc.)

---

## 📂 Dataset

**Source:** Kaggle – *Plant Pathology 2020 – FGVC7*  
The dataset consists of labeled images of apple leaves with categories such as (examples):

- Healthy
- Scab
- Rust
- Multiple diseases / complex symptoms

---

## 🧠 Model Overview

> **Note:** Adjust details here to match your actual implementation (framework, architecture, etc.).

- **Task type:** Image classification (multi-class and/or multi-label)
- **Input:** RGB leaf image
- **Output:** Disease probabilities for each class (used to compute ROC AUC)
- **Architecture:** Deep CNN / transfer learning (e.g., ResNet, EfficientNet, etc.)
- **Loss:**  
  - Multi-class: Cross-entropy  
  - Multi-label: Binary cross-entropy with logits (per class sigmoid)
- **Evaluation metric:** Mean column-wise ROC AUC over all disease labels

**Key points addressed:**

- **Rare classes:** Class weighting / data augmentation / oversampling  
- **Lighting & angle variation:** Strong augmentations (rotation, flip, brightness/contrast, etc.)  
- **Multiple diseases per leaf:** Sigmoid outputs (if modeled as multi-label) + thresholding

---

## 🌐 Farmer Web App

The web application wraps the trained model and provides:

- **Image upload** (and optionally camera capture, if implemented)
- **Server-side inference** using the trained model
- **Prediction panel** with:
  - Probability / confidence for each disease class
  - Highlight of the most likely label(s)
- **Farmer-friendly text** explaining:
  - Possible disease
  - Simple next steps / recommendation disclaimer

##Thech Stacks:
> - Backend: Flask.
> - Frontend: HTML/CSS/JS etc.
> - Model Preparation: python, tensorflow.

---

## 🛠️ Installation

Clone the repository and move into the project directory:

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
