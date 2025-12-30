# Alzheimer Detection (Unsupervised)

This project presents an unsupervised deep learning approach for detecting Alzheimer’s disease from brain images using multiscale feature extraction and flow-based anomaly detection.

Instead of learning disease labels, the model learns the distribution of healthy brain anatomy and identifies pathological deviations as anomalies.

---

## Method Overview

The system consists of three main components:

1. **Multiscale Feature Extraction**
   - ResNet18 backbone
   - Features extracted at multiple spatial resolutions

2. **Flow-Based Density Modeling**
   - FastFlow-style normalizing flows
   - Invertible 1×1 convolutions and affine coupling layers
   - Gaussian latent prior

3. **Anomaly Scoring**
   - Pixel-wise anomaly maps
   - Quantile-based aggregation (95th percentile)
   - Multiscale anomaly map fusion

---

## Why Unsupervised?

- Medical labels are expensive and noisy
- Early Alzheimer’s changes are subtle and localized
- Anomaly detection captures deviations from normal anatomy
- No disease labels are required during training

---

## Results

- Healthy and Alzheimer samples show overlapping anomaly energy distributions
- Progressive right-shift and heavier tails are observed with increasing disease severity
- Q–Q plots confirm alignment with the Gaussian prior for normal samples and deviations for pathological cases

These trends are consistent with the progressive nature of Alzheimer’s disease.

---

## Key Features

- No labeled data required
- Sensitive to localized neurodegeneration
- Robust to noise and scanner variability
- Interpretable anomaly maps

---

## Technologies

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
