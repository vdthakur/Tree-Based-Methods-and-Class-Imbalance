# Tree-Based Methods and Class Imbalance

This repository explores tree-based methods for classification, with a focus on handling missing values and addressing class imbalance using techniques like Random Forests, XGBoost, and SMOTE. The analysis is performed on the **APS Failure at Scania Trucks Dataset**.

---

## Table of Contents

- [Introduction](#introduction)
- [Data](#data)
- [Project Tasks](#project-tasks)
  - [Data Preparation](#data-preparation)
  - [Random Forest Classification](#random-forest-classification)
  - [Addressing Class Imbalance](#addressing-class-imbalance)
  - [XGBoost and Model Trees](#xgboost-and-model-trees)
  - [SMOTE and XGBoost](#smote-and-xgboost)
- [Results](#results)
---

## Introduction

This project investigates tree-based methods for classification using the **APS Failure Dataset**. The key focus areas include:
1. Handling missing data using imputation techniques.
2. Feature selection and visualization.
3. Addressing class imbalance using techniques like SMOTE.
4. Building and evaluating models like Random Forests and XGBoost with class imbalance compensation.

---

## Data

### Dataset Details:
- **Training Set**: 60,000 rows, with 1,000 belonging to the positive class.
- **Test Set**: Separate test set provided.
- **Features**: 170 numeric attributes plus one class column.
- **Challenge**: 
  - Significant class imbalance.
  - Missing values in the data.

---

## Project Tasks

### Data Preparation

1. **Handling Missing Values**:
   - Research and apply a data imputation technique to deal with missing values. Techniques may include:
     - Mean/median imputation.
     - K-Nearest Neighbors (KNN) imputation.
     - Multivariate imputation.

2. **Coefficient of Variation (CV)**:
   - Calculate the CV for each feature using:
     \[
     CV = \frac{s}{m}
     \]
     where \( s \) is the sample standard deviation and \( m \) is the sample mean.

3. **Correlation Matrix**:
   - Plot a correlation matrix to analyze relationships between features.

4. **Feature Selection and Visualization**:
   - Select \( \lfloor \sqrt{170} \rfloor \) features with the highest CV.
   - Create scatter plots and box plots for these features to visualize their distributions.

5. **Class Imbalance Analysis**:
   - Determine the number of positive and negative instances in the dataset.
   - Analyze and document the extent of class imbalance.

---

### Random Forest Classification

1. **Train a Random Forest Model**:
   - Train a Random Forest classifier without compensating for class imbalance.
   - Report the following for both training and test sets:
     - Confusion matrix.
     - ROC curve and AUC.
     - Misclassification error.

2. **Out-of-Bag (OOB) Error**:
   - Calculate the OOB error for the Random Forest model.
   - Compare the OOB error with the test error.

---

### Addressing Class Imbalance

1. **Compensate for Class Imbalance**:
   - Research methods to handle class imbalance in Random Forests (e.g., class weighting, oversampling, undersampling).
   - Train a new Random Forest model with class imbalance compensation.
   - Repeat the evaluation steps from the previous section and compare results.

---

### XGBoost and Model Trees

1. **Model Trees**:
   - Train a model tree using XGBoost without compensating for class imbalance.
   - Use L1-penalized logistic regression at each node to determine splits.
   - Tune the regularization parameter (\( \alpha \)) using cross-validation.

2. **Cross-Validation**:
   - Use one of the following methods to estimate error:
     - 5-fold cross-validation.
     - 10-fold cross-validation.
     - Leave-one-out cross-validation.
   - Report the Confusion Matrix, ROC, and AUC for both training and test sets.

---

### SMOTE and XGBoost

1. **SMOTE Pre-Processing**:
   - Use SMOTE (Synthetic Minority Over-sampling Technique) to balance the dataset before training.
   - Ensure proper handling of cross-validation to avoid data leakage.

2. **Train XGBoost with SMOTE**:
   - Train the XGBoost model with L1-penalized logistic regression at each node on the SMOTE-processed data.
   - Repeat the evaluation steps:
     - Confusion matrix.
     - ROC curve and AUC.

3. **Comparison**:
   - Compare the results of the uncompensated XGBoost model with the SMOTE-processed XGBoost model.

---

## Results

- **Data Imputation**: Selected technique and its impact on model performance.
- **Feature Selection**: Scatter and box plots for high CV features, highlighting potential significance.
- **Random Forest**:
  - Performance before and after class imbalance compensation.
  - Comparison of test errors and OOB errors.
- **XGBoost**:
  - Results for uncompensated vs. SMOTE-processed models.
  - Effectiveness of L1-penalized logistic regression at decision nodes.

---
