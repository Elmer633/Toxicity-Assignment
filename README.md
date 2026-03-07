Summary of Analysis
1. Data Overview
   
  -Dataset contains 545 samples with 1803 features

  -Highly imbalanced: 537 Non-Toxic vs 8 Toxic samples (67:1 ratio)

  -No missing values or infinite values found

2. Preprocessing Steps
   
  -Separated features and target variable

  -Encoded target labels using LabelEncoder

  -Split data into training (80%) and testing (20%) sets with stratification

  -Handled any infinite values (none found)

3. Feature Selection
   
  -Used Random Forest feature importance for selection

  -Selected 901 features out of 1803 (using median threshold)

  -Top features include various molecular descriptors (C3SP3, SRW series, SpMin8 series)

4. Model Performance
   
  -Cross-validation results (5-fold stratified):

    Average Accuracy: 98.63% (±1.44%)

    Average ROC-AUC: 99.91% (±0.15%)

  -Test set performance:

    Accuracy: 99.08%

    ROC-AUC: 100%

    Perfect classification of Toxic compound in test set

    Only 1 misclassification (Non-Toxic predicted as Toxic)

5. Key Insights
   
  -The model handles class imbalance well (using balanced class weights)

  -Ensemble approach (Random Forest + Gradient Boosting) provides robust predictions

  -Feature selection reduced dimensionality by 50% while maintaining high performance

  -Top important features are related to molecular structure and connectivity
