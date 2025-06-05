# 📡 Uncertainty Modelling of Static Laser Scanning Using Deep Learning

<p align="center">
  <strong>Tingde Liu, B. Sc.</strong><br>
  Gottfried Wilhelm Leibniz Universität Hannover · Geodätisches Institut Hannover
</p>

---

## 🧠 About

This project investigates **uncertainty modelling in static terrestrial laser scanning (TLS)** using deep learning. We propose a novel neural network architecture called **RePN**, which integrates **PointNet++** for local feature extraction and a **multilayer perceptron** (MLP) for regression. The model predicts the **range residual** (uncertainty) of TLS point cloud measurements using both **geometric** and **physically-derived features**.

The dataset was collected using a **Z+F Imager 5016** laser scanner in a controlled lab environment, with over **2.5 million points** scanned from multiple positions.

---

## 🔍 Key Features

- 📌 **RePN**: Combines PointNet++ with MLP for residual regression.
- 📌 **ReFC**: A baseline fully connected neural network model.
- 📌 **Point-level features**: Intensity, incidence angle, range, spot size, sigma distance.
- 📌 **Geometric grouping** using **KD-tree** and **Farthest Point Sampling (FPS)**.
- 📌 **Multi-Scale Grouping (MSG)** for robust feature aggregation.
- 📌 Comparison with **XGBoost** baseline.
- 📈 Metrics: R² score, RMSE, and distance calibration improvements.

---

## 🧱 Model Architecture

### RePN: PointNet++ Enhanced Regression Network

<p align="center">
  <img src="https://github.com/TingdeLiu/Uncertainty-modelling-of-static-laser-scanning-using-DL/assets/117039110/bdabb067-2ca9-4a4a-8bfb-c1afb44d165e" width="75%">
</p>

- **Input**: n × (XYZ + 4 features)
- **Grouping**: Local grouping using KD-tree (r = 0.1)
- **Sampling**: 128 samples per group (FPS)
- **MSG**: Radius = [0.035, 0.07, 0.1]; Samples = [16, 64, 128]
- **Feature Aggregation**: MLP → MaxPooling → Concat → MLP regression

---

## 📊 Results

### 🔹 RePN vs XGBoost

<p align="center">
  <img src="https://github.com/TingdeLiu/Uncertainty-modelling-of-static-laser-scanning-using-DL/assets/117039110/dc81c2ac-3dfd-4c7d-a543-18cd5680a320" width="70%">
</p>

- ✅ **Higher R² score**
- ✅ **Lower RMSE**
- ✅ **More robust generalization**

### 🔹 Residual Calibration

- Pre-calibration mean: **0.387 mm**
- Post-calibration mean: **0.009 mm**
- Standard deviation reduced by **49%**

---

## 📂 Dataset Description

| Attribute           | Value                   |
|---------------------|--------------------------|
| Scanner             | Z+F Imager 5016          |
| Location            | HiTec Lab, LUH           |
| Target              | 3D printed planar surface |
| Points              | 2,534,160                |
| Format              | n × 9 (XYZ + 6 features) |

---

## ⚙️ Training Setup

- Programming Language: Python 3.10
- Frameworks: PyTorch, NumPy, Scikit-learn
- Validation: Holdout + K-Fold Cross Validation
- Optimization: Grid Search (batch size, learning rate)

---

## 🧪 How to Use

1. Clone this repo:
   ```bash
   git clone https://github.com/TingdeLiu/Uncertainty-modelling-of-static-laser-scanning-using-DL.git
   cd Uncertainty-modelling-of-static-laser-scanning-using-DL

