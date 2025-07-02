# 🕵️‍♂️ Tampered Image Detection using CASIA v2

> Deep learning models for detecting image forgeries — tested on both clean and noisy datasets.

---

## 📝 Overview

This project focuses on detecting **image tampering** using the **CASIA v2 dataset**, a widely used benchmark for digital forensics. We evaluate the performance of multiple CNN architectures in classifying manipulated vs. authentic images.

To test the robustness of each model, we also evaluate their performance on versions of the dataset with **added noise** (Gaussian, salt-and-pepper, etc.).

---

## 🔍 Objective

- Detect tampered images (splicing, copy-move, etc.) using CNN-based classifiers.
- Evaluate model performance on clean vs. noisy data.
- Compare accuracy, robustness, and generalization of different architectures.

---

## 📦 Models Used

| Model            | Parameters | Notes                         |
|------------------|------------|-------------------------------|
| ResNet-18        | ~11M       | Baseline residual network     |
| MobileNetV3-Small| ~2.9M      | Lightweight and efficient     |
| DenseNet121      | ~7M        | Feature-dense architecture    |
| ConvNeXt-Tiny    | ~28M       | Modern CNN, transformer-style |

---

## 🧪 Dataset

- **CASIA v2**: A curated dataset of real and tampered images (with labels).
- Split: 80% training / 20% testing.
- **Noise Augmentation**:
  - Gaussian noise
  - Salt-and-pepper noise
  - Motion blur (optional)

---

## 🧠 Methodology

1. **Data Preprocessing**
   - Resize, normalize, label encoding
   - Augmentation: Random flips, crops, noise injection

2. **Training**
   - Image classification (binary: tampered vs. authentic)
   - Optimizer: Adam
   - Loss: Binary Cross Entropy
   - Evaluation: Accuracy, F1-score, ROC AUC

3. **Experiments**
   - Train/evaluate each model on clean images
   - Train/evaluate each model on noisy images
   - Compare results

---

## 📈 Results (Example Table)

| Model            | Accuracy (Clean) | Accuracy (Noisy) |
|------------------|------------------|------------------|
| ResNet-18        | 91.4%            | 83.7%            |
| MobileNetV3      | 88.9%            | 80.2%            |
| DenseNet121      | 92.1%            | 84.9%            |
| ConvNeXt-Tiny    | 93.4%            | 89.3%            |

> 📌 *ConvNeXt shows the highest robustness to noise.*

---

## ▶️ Getting Started

### Requirements

- Python 3.8+
- PyTorch
- OpenCV
- NumPy, Pandas
- scikit-learn
- torchvision
