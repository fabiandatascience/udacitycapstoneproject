# Arvato Financial Services Customer Segmentation Project

This project uses machine learning techniques to analyze customer demographics for a mail-order sales company in Germany, provided by Arvato Financial Services. The goal is to segment customers, compare them to the general population, and use insights to predict potential customers for targeted marketing campaigns.

## Project Overview

The project consists of two main tasks:
1. **Unsupervised Learning** - Performing customer segmentation using demographic data to identify unique groups within the customer base and compare them to the general population.
2. **Supervised Learning** - Building a predictive model that can identify individuals who are likely to become customers based on demographic data.

## Datasets

The project uses four datasets:
- `Udacity_AZDIAS_052018.csv`: Demographic data representing the general German population.
- `Udacity_CUSTOMERS_052018.csv`: Demographic data representing existing customers.
- `Udacity_MAILOUT_052018_TRAIN.csv`: Data for individuals targeted in a marketing campaign, including the response (customer or not).
- `Udacity_MAILOUT_052018_TEST.csv`: Similar to the training data but without the response column. Predictions will be evaluated against this dataset.

## Data Cleaning

The raw data required extensive cleaning and preprocessing:
1. **Identification and Imputation of Missing Values** - Mapped specific values to `NaN` based on DIAS Attributes.
2. **Data Reduction** - Dropped columns with high missing value rates (>30%).
3. **Mapping and Encoding** - Mapped categorical values to numerical representations and converted object columns to numeric format.
4. **Duplicate Removal** - Removed duplicate rows where applicable.
5. **Scaling and Standardization** - Scaled numerical features to ensure consistency across datasets.

## Unsupervised Learning - Customer Segmentation

Using principal component analysis (PCA) and KMeans clustering, the project creates customer segments within the demographic data:
- **PCA Transformation**: Reduced high-dimensional data into principal components, capturing the primary variations in customer demographics.
- **KMeans Clustering**: Segmented both customer and general population datasets and analyzed cluster compositions to identify overrepresented clusters in the customer dataset.

## Supervised Learning - Customer Prediction Model

A supervised learning model was trained on the `MAILOUT_TRAIN` data to predict potential customers based on demographic features:
1. **Data Preparation**: Preprocessed the `MAILOUT_TRAIN` dataset to handle missing values and scale features.
2. **Model Selection**: Random forest classifier with hyperparameter tuning using `GridSearchCV`.
3. **Evaluation**: Assessed model performance using ROC AUC scoring. The model predicts probabilities of customer conversion on the `MAILOUT_TEST` dataset for Kaggle submission.
