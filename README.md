# Robust Seed Classification Under Distribution Shift

## Overview

This project investigates the robustness of deep learning models under distribution shift and shortcut learning.

A ResNet-18 classifier was trained for seed quality classification and evaluated under multiple out-of-distribution scenarios involving pose, scale, and lighting variations.

Using Grad-CAM visualisation and targeted augmentation strategies, the study identifies hidden model vulnerabilities and develops methods to improve generalisation performance.

---

## Research Questions

1. Can deep neural networks generalise under distribution shift?

2. What visual features are driving model decisions?

3. Do models rely on meaningful morphological features or spurious shortcuts?

4. Can targeted augmentation reduce shortcut learning?

5. How can explainable AI improve model reliability?

---

## Dataset

| Feature | Description |
|----------|-------------|
| Domain | Seed Quality Classification |
| Input | RGB Images |
| Task | Multi-Class Classification |
| Architecture | ResNet-18 |

---

## Methodology

### Deep Learning

- ResNet-18
- Transfer Learning
- Data Augmentation

### Explainable AI

- Grad-CAM
- Feature Visualisation
- Saliency Analysis

### Robustness Evaluation

- Distribution Shift Testing
- Out-of-Domain Evaluation
- Performance Benchmarking

---

## Key Findings

### Strong In-Domain Performance Can Be Misleading

Models achieved high accuracy on familiar data but experienced substantial performance degradation under distribution shift.

### Grad-CAM Revealed Shortcut Learning

Visualisation techniques showed that models relied on spurious image characteristics rather than meaningful biological features.

### Augmentation Improved Generalisation

Morphological and photometric augmentation reduced shortcut dependence and improved out-of-distribution accuracy.

### Explainability Improved Model Diagnosis

Grad-CAM provided valuable insight into failure mechanisms and informed the design of more robust training pipelines.

---

## Technical Skills Demonstrated

### Machine Learning

- Deep Learning
- Transfer Learning
- Model Evaluation

### Computer Vision

- Image Classification
- Feature Extraction
- Data Augmentation

### Explainable AI

- Grad-CAM
- Model Interpretability
- Visual Analytics

### Programming

- Python
- PyTorch
- OpenCV

---

## Technologies Used

- Python
- PyTorch
- OpenCV
- NumPy
- Matplotlib

---

## Author

Kan Kai Zheng

BSc (Hons) Mathematics and Data Science
University of Nottingham Malaysia
