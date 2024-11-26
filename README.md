# Chest X-Ray Classification with VGG16

This project leverages transfer learning using the pre-trained **VGG16** model to classify chest X-ray images into five categories: **Viral Pneumonia**, **Bacterial Pneumonia**, **COVID-19**, **Tuberculosis**, and **Normal Lungs**.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Model Architecture](#model-architecture)
4. [Training Details](#training-details)
5. [Results](#results)
6. [Usage](#usage)
7. [Future Work](#future-work)

---

## Project Overview

This project aims to assist in medical diagnosis by automating the classification of chest X-rays using deep learning. The model is based on **VGG16** for feature extraction, with custom fully connected layers for classification.

---

## Dataset

- **Images**: 10,000 chest X-ray images, augmented 6x for generalization.
- **Classes**:
  1. Viral Pneumonia
  2. Bacterial Pneumonia
  3. COVID-19
  4. Tuberculosis
  5. Normal Lungs
- **Data Split**:
  - Training: 70%
  - Validation: 20%
  - Testing: 10%

---

## Model Architecture

- **Base Model**: VGG16 (pre-trained on ImageNet, frozen layers).
- **Custom Layers**:
  - Dense (256 neurons, ReLU activation)
  - Dropout (50%)
  - Dense (128 neurons, ReLU activation)
  - Dropout (50%)
  - Dense (5 neurons, Softmax activation)
- **Input Shape**: `(224, 224, 3)`

---

## Training Details

- **Optimizer**: Adam (learning rate: `0.0001`)
- **Loss Function**: Categorical Cross-Entropy
- **Metrics**: Accuracy
- **Batch Size**: 32
- **Epochs**: Up to 50 (with early stopping)
- **Callbacks**:
  - ModelCheckpoint: Save the best model.
  - EarlyStopping: Stop training after 10 epochs without improvement.

---

## Results

- **Training Accuracy**: ~94.24%
- **Validation Accuracy**: ~80.65%
- **Test Accuracy**: ~84.49%
- Performance plots (accuracy and loss) are included in the repository.

