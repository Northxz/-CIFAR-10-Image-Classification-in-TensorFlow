Here is a clean, detailed `README.md` focused purely on project information, using emojis for visual appeal.

---

# 🖼️ CIFAR-10 Image Classification with CNN

[![Python 3.12](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![Keras](https://img.shields.io/badge/Keras-API-D00000?logo=keras&logoColor=white)](https://keras.io/)

A **Convolutional Neural Network (CNN)** built with **TensorFlow/Keras** to classify images from the CIFAR-10 dataset. This project demonstrates a complete deep learning workflow including data preprocessing, model architecture design, training with regularization techniques, and performance evaluation.

---

## 📂 About the Dataset

The **CIFAR-10** dataset is a widely used benchmark in computer vision, consisting of:

- **60,000** labeled images
- **32x32** pixels in **RGB** color
- **10** mutually exclusive classes
- Split into **50,000** training and **10,000** test images

**Classes:** ✈️ Airplane • 🚗 Automobile • 🐦 Bird • 🐱 Cat • 🦌 Deer • 🐶 Dog • 🐸 Frog • 🐴 Horse • 🚢 Ship • 🚚 Truck

---

## 🧠 Model Architecture

The model employs a **deep CNN architecture** with three convolutional blocks, progressively increasing filter depth while reducing spatial dimensions. **Dropout regularization** is strategically placed to combat overfitting.

### Architecture Overview

| Block | Layers | Output Shape | Key Purpose |
|-------|--------|--------------|-------------|
| **Block 1** | Conv2D (32) → Conv2D (32) → MaxPooling → Dropout (0.25) | 16×16×32 | Low-level feature extraction |
| **Block 2** | Conv2D (64) → Conv2D (64) → MaxPooling → Dropout (0.25) | 8×8×64 | Mid-level pattern recognition |
| **Block 3** | Conv2D (128) → Conv2D (128) → MaxPooling → Dropout (0.25) | 4×4×128 | High-level feature learning |
| **Classifier** | Flatten → Dense (512) → Dropout (0.5) → Dense (10) | 10 | Final classification |

**Total Parameters:** 1,341,226 | **Trainable Parameters:** 1,341,226

---

## 📊 Performance Highlights

The model achieves strong classification performance on this challenging dataset.

| Metric | Value |
|--------|-------|
| **Test Accuracy** | **79.63%** |
| **Test Loss** | 0.6272 |
| **Training Epochs** | 30 |
| **Batch Size** | 64 |

### Training Curves

The model shows healthy learning dynamics with minimal overfitting, thanks to dropout regularization.

| Accuracy Progression | Loss Progression |
|:---:|:---:|
| *Training accuracy steadily improves while validation accuracy remains stable* | *Training and validation loss converge smoothly* |

### Prediction Examples

The model generalizes well to unseen test images across all ten classes.

| | | |
|:---:|:---:|:---:|
| **True: Cat • Pred: Cat** | **True: Ship • Pred: Ship** | **True: Truck • Pred: Truck** |
| **True: Deer • Pred: Deer** | **True: Frog • Pred: Frog** | **True: Automobile • Pred: Automobile** |

---

## 🛠️ Technical Implementation

### Key Features

- **Data Preprocessing:** Pixel normalization (0-255 → 0-1) and one-hot encoding of labels
- **Regularization:** Dropout layers (0.25 after pooling, 0.5 before final layer)
- **Optimization:** Adam optimizer with categorical cross-entropy loss
- **Validation:** 20% training/validation split for hyperparameter tuning

### Technologies Used

- **Core Framework:** TensorFlow 2.x / Keras
- **Language:** Python 3.12
- **Data Handling:** NumPy
- **Visualization:** Matplotlib
- **Development Environment:** Google Colab with GPU acceleration

---

## 📈 Key Learnings

- CNN architectures with **progressive filter increases** effectively capture hierarchical features
- **Strategic dropout placement** significantly reduces overfitting in deep networks
- **Data normalization** is crucial for stable training with RGB image data
- **Validation monitoring** helps identify optimal stopping points before overfitting
