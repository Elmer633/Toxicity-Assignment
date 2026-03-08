Toxicity Prediction Model

A machine learning model for predicting chemical toxicity using molecular descriptors. This project implements a comprehensive pipeline for data preprocessing, feature selection, and ensemble learning to classify compounds as Toxic or Non-Toxic.

📋 Project Overview

This repository contains a complete machine learning solution for toxicity prediction based on molecular descriptor data. The model uses an ensemble of Random Forest and Gradient Boosting classifiers to achieve high accuracy in distinguishing between toxic and non-toxic compounds.

Key Features

Comprehensive EDA with visualization of key molecular properties

Intelligent feature selection using Random Forest importance

Ensemble learning with soft voting for robust predictions

Handling of severe class imbalance (67:1 ratio)

Cross-validated performance with StratifiedKFold

Production-ready pipeline with saved models and preprocessors

📊 Dataset

The dataset contains 545 samples with 1803 molecular descriptor features, including:

Constitutional indices

Topological descriptors

Geometrical descriptors

Electronic descriptors

Molecular properties (LogP, Molecular Weight, etc.)


Class Distribution

Non-Toxic: 537 samples (98.5%)

Toxic: 8 samples (1.5%)


🏗️ Model Architecture

Data Preprocessing

Label encoding of target variable

Train-test split with stratification (80-20)

Standard scaling of features

Handling of missing/infinite values

Feature Selection
Random Forest-based feature importance

Median threshold selection

Reduction from 1803 to 901 features

Ensemble Model

python
Ensemble Components:
├── Random Forest (200 estimators, max_depth=15)
└── Gradient Boosting (200 estimators, max_depth=5, learning_rate=0.1)
└── Soft voting classifier

📈 Performance Metrics

Cross-Validation Results (5-fold)

Metric	Score	Std Dev

Accuracy	98.63%	±1.44%

ROC-AUC	99.91%	±0.15%

Test Set Performance

Metric	Score

Accuracy	99.08%

ROC-AUC	100%

Classification Report

text
              precision    recall  f1-score   support
    NonToxic       1.00      0.99      1.00       108
       Toxic       0.50      1.00      0.67         1
       
🚀 Quick Start
Prerequisites
bash
pip install -r requirements.txt
Basic Usage
python
import joblib
import pandas as pd

# Load the model and preprocessors
model = joblib.load('toxic_prediction_model.pkl')
label_encoder = joblib.load('label_encoder.pkl')
feature_selector = joblib.load('feature_selector.pkl')

# Prepare your data (should have same features as training data)
# X_new = your_new_data[selected_features]

# Make predictions
predictions = model.predict(X_new)
probabilities = model.predict_proba(X_new)

# Decode predictions
predicted_labels = label_encoder.inverse_transform(predictions)
Training Your Own Model
python
python train_model.py --data data.csv --output models/
