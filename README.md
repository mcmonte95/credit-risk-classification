# Credit Risk Analysis Challenge

## Table of Contents
- [Project Overview](#project-overview)
- [Credit Risk Analysis Report](#credit-risk-analysis-report)
  - [Analysis](#analysis)
    - [Data Splitting](#data-splitting)
    - [Logistic Regression Model with Original Data](#logistic-regression-model-with-original-data)
    - [Resampling Training Data](#resampling-training-data)
    - [Logistic Regression Model with Resampled Data](#logistic-regression-model-with-resampled-data)
    - [Model Evaluation](#model-evaluation)
  - [Results](#results)

## Project Overview
This analysis aims to build and evaluate machine learning models to determine the creditworthiness of borrowers. Using historical lending data from a peer-to-peer lending services company, we explore logistic regression's effectiveness in classifying loans as either healthy (0) or high-risk (1). We compare models trained on original and resampled data to identify the best approach for assessing loan risk. This analysis was done for educational purposes only and does not compromise anyone's personal financial information.

## Credit Risk Analysis Report

### Analysis

#### Data Splitting
- The dataset was loaded from `lending_data.csv`, resulting in a DataFrame split into features (X) and labels (y), where `loan_status` served as the labels which can either be healthy (0) or high-risk (1).
- Data was divided into training and testing sets using `train_test_split`.

#### Logistic Regression Model with Original Data
- A logistic regression model was trained using the original training data.
- Predictions were made on the testing data to evaluate the model's performance.

#### Resampling Training Data
- To address class imbalance, the training data was resampled using `RandomOverSampler` from `imblearn.over_sampling`.
- This approach aimed to increase the number of instances for the minority class in the training set, creating a balanced distribution.

#### Logistic Regression Model with Resampled Data
- A second logistic regression model was trained using the resampled training data.
- Predictions from this model were also evaluated against the testing data.

#### Model Evaluation
- **Confusion Matrix and Classification Report**: Generated for both models to assess performance.
- **Accuracy, Precision, and Recall Scores**: Calculated to compare the effectiveness of models trained on original vs. resampled data.

### Results

#### Machine Learning Model 1: Original Data
- **Balanced Accuracy Score**: Not explicitly provided, but the overall accuracy is 99%.
- **Precision and Recall Scores**:
  - **Healthy Loan**:
    - Precision: 1.00
    - Recall: 1.00
  - **High-Risk Loan**:
    - Precision: 0.87
    - Recall: 0.89
- **Overall**:
  - Accuracy: 99%
  - Macro Average Precision and Recall: 94%
  - Weighted Average Precision and Recall: 99%

#### Machine Learning Model 2: Resampled Data
- **Balanced Accuracy Score**: Not explicitly provided, but the overall accuracy is 100%.
- **Precision and Recall Scores**:
  - **Healthy Loan**:
    - Precision: 1.00
    - Recall: 1.00
  - **High-Risk Loan**:
    - Precision: 0.87
    - Recall: 1.00
- **Overall**:
  - Accuracy: 100%
  - Macro Average Precision and Recall: 94% (Precision), 100% (Recall)
  - Weighted Average Precision and Recall: 100%

