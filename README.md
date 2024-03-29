# Credit Risk Analysis Challenge

## Table of Contents
- [Project Overview](#project-overview)
- [Repository Guide](#repository-guide)
- [Credit Risk Analysis Report](#credit-risk-analysis-report)
  - [Analysis](#analysis)
    - [Data Splitting](#data-splitting)
    - [Logistic Regression Model with Original Data](#logistic-regression-model-with-original-data)
    - [Resampling Training Data](#resampling-training-data)
    - [Logistic Regression Model with Resampled Data](#logistic-regression-model-with-resampled-data)
    - [Model Evaluation](#model-evaluation)
  - [Results](#results)
    - [Model Comparison](#model-comparison)
    - [Summary](#summary)

## Project Overview
This analysis aims to build and evaluate machine learning models to determine the creditworthiness of borrowers. Using historical lending data from a peer-to-peer lending services company, we explore logistic regression's effectiveness in classifying loans as either healthy (0) or high-risk (1). We compare models trained on original and resampled data to identify the best approach for assessing loan risk. This analysis was done for educational purposes only and does not compromise anyone's personal financial information.

## Repository Guide

This repository contains two major components:

- **Resources Folder**: This folder contains the raw data file `lending_data.csv`. This CSV file holds the historical lending activity data from a peer-to-peer lending services company, which is used for our credit risk analysis.

- **Credit_Risk Folder**: Inside this folder, you will find the `credit_risk_classification.ipynb` Jupyter notebook. This notebook contains all the steps undertaken for data splitting, model training, and analysis. 

The Credit Risk Analysis Report is included as part of this README.

## Credit Risk Analysis Report

### Analysis

#### Data Splitting
- The dataset was loaded from `lending_data.csv`, and then split into features (X) and labels (y), where `loan_status` served as the labels which can either be healthy (0) or high-risk (1).
- The balance of the classes within the y values was then checkeded using `value_counts`. We can see an inbalance between the healthy (0) and the high-risk (1) classes.
- Data then was divided into training and testing sets using `train_test_split` from the `scikit-learn` python library. Using this fucntion allows for a quick way to divide the training and testing data properly.

#### Logistic Regression Model with Original Data
- A logistic regression model with `random_state=1` was trained using the original training data.
- Predictions were made on the testing data to evaluate the model's performance.

#### Model Evaluation
- **Balanced Accuracy Score, Confusion Matrix and Classification Report**: Generated for the model to assess performance.
- **Accuracy, Precision, and Recall Scores**: Pulled from the classification report.

#### Resampling Training Data
- To address class imbalance, the training data was resampled using `RandomOverSampler` from `imblearn.over_sampling`.
- This approach aimed increase the amount of high-risk (0) classes in the training data and balance the out the class distribution. This was confirmed when calling `value_counts` on the `y_train_resampled` data.

#### Logistic Regression Model with Resampled Data
- A second logistic regression model was trained using the resampled training data.
- Predictions from this model were also evaluated against the testing data.
- The same model evaulation was then done on this new model.

### Results

#### Model Comparison

| Logistic Regression Model 1: Original Data | Logistic Regression Model 2: Resampled Data |
|--------------------------------------------|---------------------------------------------|
| **Balanced Accuracy Score**: 94.4%         | **Balanced Accuracy Score**: 99.6%          |
|                                            |                                             |
| **Precision, Recall, and F1-Score**:       | **Precision, Recall, and F1-Score**:        |
| **Healthy Loan**:                          | **Healthy Loan**:                           |
| - Precision: 1.00                          | - Precision: 1.00                           |
| - Recall: 1.00                             | - Recall: 1.00                              |
| - F1-Score: 1.00                           | - F1-Score: 1.00                            |
| **High-Risk Loan**:                        | **High-Risk Loan**:                         |
| - Precision: 0.87                          | - Precision: 0.87                           |
| - Recall: 0.89                             | - Recall: 1.00                              |
| - F1-Score: 0.88                           | - F1-Score: 0.93                            |
|                                            |                                             |
| **Overall Scores**:                        | **Overall Scores**:                         |
| - Accuracy: 99%                            | - Accuracy: 100%                            |
| - Macro Average:                           | - Macro Average:                            |
|   - Precision: 94%                         |   - Precision: 94%                          |
|   - Recall: 94%                            |   - Recall: 100%                            |
|   - F1-Score: 94%                          |   - F1-Score: 96.5%                         |
| - Weighted Average:                        | - Weighted Average:                         |
|   - Precision: 99%                         |   - Precision: 100%                         |
|   - Recall: 99%                            |   - Recall: 100%                            |
|   - F1-Score: 99%                          |   - F1-Score: 100%                          |


#### Summary

We can observe that both models are quite accurate, demonstrating strong overall scores in precision and recall metrics. However, they are not 100% perfect in predicting high-risk loans (classes). This limitation is more apparent in the first regression model, as it was evident even before the model training that the imbalance in the classes could affect the ability to predict a high-risk loan. This is why resampling the data proved to be a beneficial strategy, as it allowed for more extensive training on the high-risk class. This approach resulted in a more accurate model overall, with higher scores in every critical metric. I would definitely recommend Model 2 over Model 1 for use in determining loan risk. However, I would also include a disclaimer that there is still room for improvement in the model's ability to predict high-risk classes over time as new data is gathered.
