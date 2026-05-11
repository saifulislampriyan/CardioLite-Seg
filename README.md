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
```

---

## Dataset

This project uses the **Task02_Heart** dataset from the Medical Segmentation Decathlon.

The dataset contains cardiac MRI images designed for heart structure segmentation tasks.

Dataset source:

```text
Medical Segmentation Decathlon - Task02_Heart
```

---

## Preprocessing Techniques

The project applies several preprocessing techniques to improve image quality and prepare the dataset for deep learning models.

Main preprocessing steps include:

- Image resizing
- Normalization
- MRI slice extraction
- Data formatting
- Image reconstruction preparation
- Train-test splitting

Additional image processing techniques discussed in the project include:

- Otsu thresholding
- Adaptive thresholding
- Region growing
- Watershed algorithm
- Sobel edge detection
- Canny edge detection

---

## Model Optimization Strategy

The main contribution of this project is computational optimization.

The following techniques are used or investigated:

- Separable convolution
- Depthwise separable convolution
- Reduced model complexity
- Efficient CNN blocks
- Lightweight recurrent architecture
- FLOP reduction
- Inference-time comparison

---

## Experimental Results

The optimized models achieved significant reductions in computational cost compared with the base models.

| Model | Base FLOPs | Optimized FLOPs | FLOP Reduction | Base Inference Time | Optimized Inference Time |
|---|---:|---:|---:|---:|---:|
| Autoencoder | 37,043,235,904 | 18,059,822,400 | 51.3% | 3.43s | 2.33s |
| CNN | 19,385,922,316 | 1,914,241,024 | 90.1% | 2.01s | 1.78s |
| RNN | 1,130,624 | 54,400 | 95.2% | 1.43s | 1.25s |

---

## Performance Summary

| Model | Base Accuracy | Optimized Accuracy | Observation |
|---|---:|---:|---|
| Autoencoder | 97% | 97% | Maintained performance with reduced FLOPs |
| CNN | 89% | 89% | Major FLOP reduction with stable accuracy |
| RNN | 89% | 89% | Significant computational reduction |

---

## Project Structure

```text
CardioLite-Seg/
│
├── data/
│   └── Task02_Heart/
│
├── notebooks/
│   └── Autoencoders_CNN_RNN.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── autoencoder.py
│   ├── cnn_model.py
│   ├── rnn_model.py
│   ├── train.py
│   └── evaluate.py
│
├── results/
│   ├── figures/
│   ├── graphs/
│   └── tables/
│
├── models/
│   ├── base_models/
│   └── optimized_models/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/cardiolite-seg.git
cd cardiolite-seg
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment:

For Windows:

```bash
venv\Scripts\activate
```

For Linux or macOS:

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Requirements

Main libraries used in this project:

```text
tensorflow
keras
numpy
pandas
matplotlib
opencv-python
scikit-learn
nibabel
seaborn
```

Install manually:

```bash
pip install tensorflow keras numpy pandas matplotlib opencv-python scikit-learn nibabel seaborn
```

---

## How to Run

### Run the Notebook

Open the notebook:

```text
notebooks/Autoencoders_CNN_RNN.ipynb
```

Run all cells sequentially.

---

### Train Model Using Script

```bash
python src/train.py
```

---

### Evaluate Model

```bash
python src/evaluate.py
```

---

## Results Visualization

The project includes:

- Training accuracy curves
- Training loss curves
- Reconstruction output comparison
- Base model vs optimized model comparison
- FLOP reduction tables
- Inference-time comparison

---

## Main Contribution

The main contribution of this project is not the invention of a completely new deep learning architecture.

Instead, the contribution is an **efficiency-focused optimization study** of existing deep learning models for cardiac MRI analysis.

The project demonstrates that computational cost can be reduced significantly using lightweight model design while maintaining similar performance in preliminary experiments.

---

## Limitations

This project has some limitations:

- Evaluation is performed on a limited dataset
- More advanced segmentation metrics such as Dice Score and IoU should be added
- Patient-wise train-test splitting should be strictly ensured
- More baseline models should be compared
- External validation datasets should be used
- Clinical validation is not performed
- Deployment testing on edge devices is not included yet

---

## Future Work

Future improvements may include:

- Adding U-Net, Attention U-Net, Mobile U-Net, and nnU-Net baselines
- Evaluating Dice coefficient, IoU, HD95, sensitivity, and specificity
- Performing patient-wise cross-validation
- Testing on larger cardiac MRI datasets
- Adding external validation using ACDC or M&Ms dataset
- Implementing pruning and quantization
- Exporting models to ONNX
- Testing deployment using TensorRT or ONNX Runtime
- Adding Grad-CAM or explainability-based visualization
- Improving clinical interpretability

---

## Suggested Evaluation Metrics for Future Version

For a stronger medical image segmentation study, the following metrics should be included:

| Metric | Purpose |
|---|---|
| Dice Coefficient | Measures overlap between prediction and ground truth |
| IoU / Jaccard Index | Measures segmentation similarity |
| HD95 | Measures boundary error |
| Precision | Measures false positive control |
| Recall / Sensitivity | Measures missed region control |
| Specificity | Measures background classification |
| FLOPs | Measures computational cost |
| Parameters | Measures model size |
| Inference Time | Measures deployment speed |
| Memory Usage | Measures hardware efficiency |

---

## Technologies Used

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" />
  <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenCV-27338e?style=for-the-badge&logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
</p>

---

## Academic Context

This project was developed as a research/thesis project in the field of:

```text
Machine Learning
Deep Learning
Medical Image Analysis
Cardiac MRI Segmentation
Computational Optimization
```

---

## Disclaimer

This project is intended for academic and research purposes only.

It is not clinically validated and should not be used for medical diagnosis or treatment decisions.

---

## Citation

If you use this project or find it helpful, please cite or acknowledge it as:

---

## License

This project is released for academic and research use.

---
