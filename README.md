# Instance Hardness-Based Relevance for Imbalanced Regression

This repository contains the implementation of the approach proposed in the paper:

**"Instance Hardness–Based Relevance for Imbalanced Regression"**  

---

## 📌 Overview

Imbalanced regression problems occur when certain regions of the target variable are underrepresented, leading machine learning models to perform poorly in those areas.

Traditional methods rely on **relevance functions (ϕ)** to identify rare instances. However, these methods struggle in more complex scenarios such as **bimodal distributions**, where rarity cannot be inferred solely from the target variable.

This project proposes a novel approach:

> 🔍 **Instance Hardness-based Relevance Function (IH-based)**

Instead of relying only on statistical rarity, this method uses **prediction difficulty (Instance Hardness)** to identify rare instances.

---

## 🚀 Key Contributions

- 📊 Introduces a new relevance function based on **Instance Hardness**
- 🎯 Improves identification of rare instances in **imbalanced regression**
- 📈 Handles complex distributions (e.g., bimodal)
- 🔄 Enhances performance of balancing techniques:
  - Random Oversampling (RO)
  - Gaussian Noise (GN)

---

## 🧠 How It Works

The method assigns a relevance score to each instance based on its prediction difficulty:

- Values range from **0 to 1**
- Instances closer to **1 → harder to predict → considered rare**

### Steps:

1. Train a pool of regression models
2. Compute prediction errors for each instance
3. Aggregate errors into an **Instance Hardness (IH) score**
4. Define a threshold (e.g., top 30%)
5. Label instances as:
   - Rare (high IH)
   - Normal (low IH)

---

## 📊 Experimental Setup

- 📁 **29 datasets**
- 🤖 Models used:
  - Random Forest (RF)
  - Bagging (BG)
  - XGBoost (XGB)
  - SVR
  - MLP

- 🔁 Validation:
  - Repeated K-Fold (2x5)

- 📏 Metrics:
  - MAE (Mean Absolute Error)
  - MSE (Mean Squared Error)

---

## 📈 Results

- ✅ Better performance in ~70% of experiments
- 📊 Improved balancing effectiveness compared to:
  - Traditional relevance function (ϕ)
  - Distance-based relevance (DRF)

- 🔥 Strong performance especially in:
  - **Bimodal distributions**
  - Complex data scenarios

---

## 📂 Project Structure

```
├── data/ # Datasets used in experiments
├── exploratory_analyzes/ # Exploratory data analysis scripts and notebooks
├── ih_based_function/ # Implementation of the IH-based relevance function
├── resampling/ # Resampling strategies (RO, GN, etc.)
├── results_data/ # Experimental results and outputs
```