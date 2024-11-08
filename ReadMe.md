# Credit Risk Prediction using Machine Learning

## Project Overview
This project aims to develop a machine learning model to predict the credit risk of customers at a German bank. The primary focus is on accurately identifying high-risk customers, thereby enabling the bank to make informed lending decisions while managing potential financial losses.

## Table of Contents
- [Installation](#installation)
- [Data Description](#data-description)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling](#modeling)
- [Model Evaluation](#model-evaluation)
- [Results](#results)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [License](#license)

## Installation
To run this project, ensure you have the following dependencies installed:
pip install pandas numpy matplotlib seaborn scikit-learn xgboost category_encoders scikit-optimize

## Data Description
The dataset used in this project contains 1,000 entries with 10 features, including:
- **Age**: Age of the customer
- **Sex**: Gender of the customer (male/female)
- **Job**: Job type (encoded as integers)
- **Housing**: Housing status (own/rent/free)
- **Saving accounts**: Status of savings accounts
- **Checking account**: Status of checking accounts
- **Credit amount**: Amount of credit requested
- **Duration**: Duration of the credit in months
- **Purpose**: Purpose of the credit
- **Risk**: Target variable indicating credit risk (good/bad)

The dataset has missing values in the "Saving accounts" and "Checking account" columns, which are addressed during preprocessing.

## Exploratory Data Analysis (EDA)
The EDA phase involved:
- Analyzing the distribution of features and the target variable.
- Identifying and visualizing missing values and outliers.
- Understanding the relationships between features and the target variable using various plots (e.g., histograms, boxplots, countplots).
- Assessing feature importance and correlations.

Key insights from the EDA include:
- Younger customers tend to exhibit higher credit risk.
- Higher credit amounts are associated with increased risk.
- Customers with longer credit durations are more likely to default.

## Modeling
The modeling phase includes:
1. **Data Preprocessing**: Handling missing values, encoding categorical features, and scaling numerical features.
2. **Model Selection**: Various models were evaluated, including:
   - Logistic Regression
   - Support Vector Machines (SVM)
   - K-Nearest Neighbors (KNN)
   - Random Forest
   - XGBoost
   - Neural Networks

3. **Hyperparameter Tuning**: Bayesian optimization was used to fine-tune the hyperparameters of the Random Forest and Logistic Regression models.

## Model Evaluation
The models were evaluated using stratified k-fold cross-validation, focusing on the ROC-AUC score to assess performance. The Random Forest model showed signs of overfitting, while Logistic Regression provided a good balance between training and validation scores.

### Key Metrics
- **Best Mean Test Score**: Random Forest: 0.764, Logistic Regression: 0.759
- **Recall**: Increased from 0.72 to 0.85 by adjusting the classification threshold.

## Results
The final model, a tuned Random Forest Classifier, achieved:
- **Recall**: 85% of high-risk customers correctly identified.
- **Precision**: 47%, indicating a trade-off between precision and recall.

### Top Predictions
- The model identified the top 10 customers with the highest estimated probabilities of being high-risk.

## Conclusion
This project successfully developed a machine learning model to predict credit risk, focusing on maximizing recall to identify high-risk customers. The EDA provided valuable insights into credit risk patterns, and various modeling techniques were employed to achieve the desired outcomes.

## Future Work
Future enhancements could include:
- Implementing a CI/CD pipeline for model deployment.
- Exploring additional features or external datasets to improve model performance.
- Investigating advanced techniques for handling imbalanced datasets.
