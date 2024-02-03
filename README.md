# Credit Risk Analysis Challenge

## Table of Contents
- [Overview](#overview)
- [Analysis](#analysis)
  - [Data Splitting](#data-splitting)
  - [Logistic Regression Model with Original Data](#logistic-regression-model-with-original-data)
  - [Resampling Training Data](#resampling-training-data)
  - [Logistic Regression Model with Resampled Data](#logistic-regression-model-with-resampled-data)
  - [Model Evaluation](#model-evaluation)
- [Comparison of Models](#comparison-of-models)
- [Summary](#summary)

## Overview
This analysis aims to build and evaluate machine learning models to determine the creditworthiness of borrowers. Using historical lending data from a peer-to-peer lending services company, we explore logistic regression's effectiveness in classifying loans as either healthy (0) or high-risk (1). We compare models trained on original and resampled data to identify the best approach for assessing loan risk. This analysis was done for educational purposes only and does not compromise anyones personal financial information.

## Analysis

### Data Splitting
- The dataset was loaded from `lending_data.csv`, resulting in a DataFrame split into features (X) and labels (y), where `loan_status` served as the labels which can either be healthy (0) or high-risk (1).
- Data was divided into training and testing sets using `train_test_split`.

### Logistic Regression Model with Original Data
- A logistic regression model was trained using the original training data.
- Predictions were made on the testing data to evaluate the model's performance.

### Resampling Training Data
- To address class imbalance, the training data was resampled using `RandomOverSampler` from `imblearn.over_sampling`.
- This approach aimed to increase the number of instances for the minority class in the training set, creating a balanced distribution.

### Logistic Regression Model with Resampled Data
- A second logistic regression model was trained using the resampled training data.
- Predictions from this model were also evaluated against the testing data.

### Model Evaluation
- **Confusion Matrix and Classification Report**: Generated for both models to assess performance.
- **Accuracy, Precision, and Recall Scores**: Calculated to compare the effectiveness of models trained on original vs. resampled data.

## Analysis Report
An analysis report was completed to evaluate the performance of both models and assess the results
