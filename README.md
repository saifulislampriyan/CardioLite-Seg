# CardioLite-Seg: Lightweight Deep Learning for Cardiac MRI Segmentation

<p align="center">
  <img src="https://img.shields.io/badge/Deep%20Learning-Cardiac%20MRI-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Task-Medical%20Image%20Segmentation-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Framework-TensorFlow%20%7C%20Keras-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Research%20Project-purple?style=for-the-badge" />
</p>

---

## Overview

**CardioLite-Seg** is a lightweight deep learning research project for **cardiac MRI image analysis and segmentation**.

This project is based on an existing hybrid deep learning approach that integrates **Autoencoders, Convolutional Neural Networks, and Recurrent Neural Networks** for cardiac MRI analysis.

The main goal of this work is to reduce computational cost while maintaining competitive model performance. To achieve this, optimized model variants are developed using lightweight architectural components such as **separable convolutional layers**, reduced parameter complexity, and efficient recurrent modeling.

This project was developed as part of an undergraduate research/thesis work in Computer Science and Engineering.

---

## Key Objectives

- Develop lightweight deep learning models for cardiac MRI analysis
- Reduce computational cost measured by FLOPs
- Improve inference efficiency
- Compare base and optimized model architectures
- Evaluate Autoencoder, CNN, and RNN-based approaches
- Investigate the trade-off between performance and computational efficiency

---

## Research Motivation

Cardiac MRI segmentation is an important task in medical imaging because it helps clinicians analyze heart structures more accurately.

However, many deep learning-based medical image analysis models are computationally expensive and difficult to deploy in low-resource environments.

This project focuses on making deep learning models more economical by reducing computational complexity while trying to preserve model performance.

---

## Proposed Approach

The project evaluates three types of deep learning models:

### 1. Autoencoder

The Autoencoder is used for image reconstruction, feature extraction, and representation learning.

**Optimization strategy:**

- Replacing standard convolutional layers with lightweight convolutional operations
- Reducing computational complexity
- Maintaining reconstruction quality

---

### 2. Convolutional Neural Network

The CNN model is used for spatial feature extraction and cardiac MRI image analysis.

**Optimization strategy:**

- Using `SeparableConv2D` layers
- Reducing FLOPs
- Improving inference efficiency
- Preserving classification/segmentation-related performance

---

### 3. Recurrent Neural Network

The RNN model is used to analyze sequential or structured information extracted from MRI data.

**Optimization strategy:**

- Reducing recurrent computation
- Using a lightweight recurrent design
- Improving inference speed
- Lowering model complexity

---

## System Architecture

```text
Input Cardiac MRI Images
        |
        v
Data Preprocessing
        |
        v
---------------------------------
| Autoencoder Feature Learning  |
---------------------------------
        |
        v
---------------------------------
| CNN Spatial Feature Analysis  |
---------------------------------
        |
        v
---------------------------------
| RNN Sequential Feature Model  |
---------------------------------
        |
        v
Model Evaluation and Comparison
        |
        v
Optimized Lightweight Models
