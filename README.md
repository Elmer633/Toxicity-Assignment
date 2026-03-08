# Toxicity Prediction using Machine Learning

## Overview

This project builds a **machine learning model to predict chemical toxicity** based on molecular descriptors. The workflow includes data exploration, preprocessing, feature selection, model training, and evaluation using ensemble learning techniques.

The goal is to automatically classify compounds as **toxic or non-toxic** using statistical and machine learning methods.

---

## Project Objectives

* Analyze and understand the distribution of chemical descriptor data.
* Detect and handle issues such as **missing values, infinite values, and class imbalance**.
* Perform **feature selection** to identify the most important molecular descriptors.
* Train and evaluate **ensemble machine learning models**.
* Save the trained model for future predictions.

---

## Dataset

The dataset contains **chemical compounds described by multiple molecular descriptors**, including features such as:

* `XLogP` – Lipophilicity
* `MW` – Molecular Weight
* `nHBDon` – Number of Hydrogen Bond Donors
* `nHBAcc` – Number of Hydrogen Bond Acceptors
* `nRotB` – Number of Rotatable Bonds
* `TopoPSA` – Topological Polar Surface Area

The target variable:

* **Class**

  * `Toxic`
  * `Non-Toxic`

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

The project begins by analyzing the dataset to understand:

* Class distribution
* Missing values
* Infinite values
* Feature variance
* Feature distributions
* Correlation with the target variable

Visualizations are created using **Matplotlib** and **Seaborn**.

---

### 2. Data Preprocessing

The following preprocessing steps are applied:

* Separating **features (X)** and **target variable (y)**
* Encoding categorical labels using **LabelEncoder**
* Handling missing and infinite values
* Standardizing numerical features using **StandardScaler**

---

### 3. Train-Test Split

The dataset is split into training and testing sets using:

* `train_test_split`
* Stratified sampling to preserve class distribution

---

### 4. Feature Selection

Feature selection is performed using a **Random Forest classifier** to identify the most important features.

Benefits:

* Reduces dimensionality
* Improves model performance
* Removes irrelevant descriptors

---

### 5. Model Building

An **ensemble learning approach** is used combining:

* **Random Forest Classifier**
* **Gradient Boosting Classifier**

These models are integrated in a **pipeline** for preprocessing and classification.

---

### 6. Model Evaluation

The trained model is evaluated using:

* **Accuracy**
* **ROC-AUC Score**
* **Cross-validation**

This ensures the model performs well and generalizes to unseen data.

---

### 7. Feature Importance Analysis

The importance of each selected feature is analyzed using the trained Random Forest model to determine which molecular descriptors contribute most to toxicity prediction.

---

### 8. Model Saving

The trained pipeline and preprocessing components are saved for reuse using **Joblib**.

Saved files include:

```
toxic_prediction_model.pkl
label_encoder.pkl
feature_selector.pkl
```

These can later be loaded to perform predictions on new chemical data.

---

## Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib

---

## Project Structure

```
Toxicity-Prediction/
│
├── Toxicity.ipynb
├── toxic_prediction_model.pkl
├── label_encoder.pkl
├── feature_selector.pkl
├── README.md
└── dataset.csv


