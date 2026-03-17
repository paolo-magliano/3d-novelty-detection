# 3D Semantic Novelty Detection on Point Clouds

Implementation and evaluation of **semantic novelty detection methods** for 3D point clouds, focusing on **synthetic-to-real generalization** scenarios.

The project investigates how deep learning models can detect **out-of-distribution (OOD)** samples in 3D data, combining **discriminative and representation-based approaches**.  
Developed as part of the *Advanced Machine Learning* course at Politecnico di Torino.

---

## Features

- Implementation of **3D semantic novelty detection pipelines**
- Evaluation on **synthetic-to-real domain shift scenarios**
- Comparison of **discriminative and distance-based methods**
- Analysis of **failure cases and model generalization**
- Exploration of **pretrained 3D embeddings (OpenShape / Uni3D)**

---

## Overview

The task consists of identifying whether a 3D point cloud belongs to the **nominal data distribution (ID)** or is **out-of-distribution (OOD)**.

Unlike standard classification, the model must detect **previously unseen object categories**, making this an **open-set recognition problem in 3D space** :contentReference[oaicite:0]{index=0}.

The project focuses on a **synthetic-to-real setting**, where models trained on synthetic data are evaluated on real-world samples, introducing both:

- **Semantic shift** (new object categories)
- **Domain shift** (distribution mismatch between training and test data) :contentReference[oaicite:1]{index=1}

---

## Models and Methods

### Backbone Models

- **PointNet++**
- **DGCNN**

These architectures are designed to process **unordered point clouds** while ensuring:

- **Permutation invariance**
- **Geometric transformation invariance** :contentReference[oaicite:2]{index=2}

---

### Novelty Detection Approaches

- **Discriminative methods**
  - Maximum Softmax Probability (MSP)
  - Cross-Entropy-based scoring

- **Representation & Distance-based methods**
  - Feature embedding extraction
  - Distance-based scoring (e.g., L2 distance)

- **Pretrained embeddings**
  - OpenShape
  - Uni3D

These methods estimate a **normality score** indicating how far a sample lies from the nominal data distribution :contentReference[oaicite:3]{index=3}.

---

## Methodology

- Point cloud preprocessing and feature encoding  
- Training of baseline classification models  
- Implementation of novelty detection scoring functions  
- Evaluation under **domain shift conditions**  
- Comparative analysis between:
  - trained vs pretrained representations  
  - discriminative vs distance-based approaches  

---

## Results

- **Distance-based methods on pretrained embeddings** showed strong generalization  
- **Discriminative approaches** struggled under domain shift  
- Synthetic-to-real transfer highlighted significant performance gaps  
- Model performance strongly depends on:
  - embedding quality  
  - distance metric choice  
  - pretraining dataset overlap  

---

## Report

A detailed description of the methodology, experiments, and analysis is available in:

📄 `report.pdf`

---

## Notes

This project highlights key challenges in **3D open-set recognition**, including:

- Handling **non-Euclidean data representations** (point clouds)  
- Robustness under **domain shift (synthetic → real)**  
- Trade-offs between **supervised and representation-based methods**  

It also explores how **foundation models for 3D data** can improve generalization without task-specific training.
