# Credit Risk Analysis Challenge

## Table of Contents
- [Overview](#overview)
- [Results](#results)
  - [Data Splitting](#data-splitting)
  - [Logistic Regression Model with Original Data](#logistic-regression-model-with-original-data)
  - [Resampling Training Data](#resampling-training-data)
  - [Logistic Regression Model with Resampled Data](#logistic-regression-model-with-resampled-data)
  - [Model Evaluation](#model-evaluation)
- [Comparison of Models](#comparison-of-models)
- [Summary](#summary)

## Overview
This analysis aims to build and evaluate machine learning models to determine the creditworthiness of borrowers. Using historical lending data from a peer-to-peer lending services company, we explore logistic regression's effectiveness in classifying loans as either healthy (0) or high-risk (1) of defaulting. We compare models trained on original and resampled data to identify the best approach for assessing loan risk. This analysis was done for educational purposes only and does not compromise anyones personal financial information.

## Results

### Data Splitting
- The dataset was loaded from `lending_data.csv`, resulting in a DataFrame split into features (X) and labels (y), where `loan_status` served as the label.
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

## Comparison of Models
The comparison between the logistic regression models trained on original and resampled data revealed significant insights:
- **Model Trained on Original Data**: Showed high accuracy but possibly lower performance metrics for the minority class due to class imbalance.
- **Model Trained on Resampled Data**: Generally exhibited improved recall for the minority class, indicating a better ability to identify high-risk loans, potentially at the cost of a slight increase in false positives.
- **Overall Assessment**: The resampling approach helped in achieving a more balanced performance across classes, making the model trained on resampled data potentially more suitable for applications where identifying high-risk loans is critical.
