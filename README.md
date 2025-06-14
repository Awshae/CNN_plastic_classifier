## Plastic Waste Classifier using CNN & MobileNetV2

This repository contains a binary image classifier that detects whether an object is **plastic waste** or **non-plastic trash** using **MobileNetV2** and **TensorFlow/Keras**.

The model is trained on a custom image dataset with transfer learning and fine-tuning techniques. It outputs whether an input image contains plastic or not.

---

## Dataset Structure

The dataset must be arranged into `train/`, `val/`, and `test/` folders with subfolders representing each class.

---

## Model Architecture

- **Base Model**: [MobileNetV2](https://arxiv.org/abs/1801.04381) pretrained on ImageNet.
- **Custom Classification Head**:
  - `GlobalAveragePooling2D`
  - `Dropout(0.2)`
  - `Dense(1, activation='sigmoid')`

Two-phase training strategy:
1. **Initial Training** with base model frozen.
2. **Fine-Tuning** the top layers of MobileNetV2.

---

## Folder Structure

├── dataset/                 # Image data
├── train.py                 # Model training and evaluation script
├── plastic_classifier.h5    # Saved model
├── requirements.txt         # Python dependencies
├── README.md                # This file

