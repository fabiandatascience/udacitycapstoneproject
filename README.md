# Arvato Financial Services Customer Segmentation Project

This project uses machine learning techniques to analyze customer demographics for a mail-order sales company in Germany, provided by Arvato Financial Services. The goal is to segment customers, compare them to the general population, and use insights to predict potential customers for targeted marketing campaigns.

## Blogpost

The blog post for the Jupyter notebook is available on [Medium](https://medium.com/@fabian.hoetzel/customer-segmentation-and-prediction-for-arvato-financial-services-using-data-science-c1462afe5c22).  
Additionally, the Jupyter notebook is also available as an [HTML file in the repository](link_to_html_file_in_repository).


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


## Acknowledgements

This project was made possible through the **Udacity Data Science Nanodegree program** in collaboration with **AZ Direct GmbH**. I would like to acknowledge and thank both Udacity and AZ Direct GmbH for providing the resources, data, and guidance that were instrumental in completing this project.

### Dataset Credit and Terms of Use

The dataset used in this project is provided by **AZ Direct GmbH** and is intended solely for educational purposes within the **Unsupervised Learning** and **Bertelsmann Capstone** projects. In accordance with AZ Direct GmbH's General Terms, the data was accessed and used exclusively to fulfill the requirements of this capstone project as part of the Udacity Data Science Nanodegree program.

Terms of Use:
- This dataset is restricted to the context of the **Bertelsmann Capstone** and **Unsupervised Learning** projects and may not be used outside of these parameters.
- All data must be deleted within two weeks of project completion.
- Access to the data is granted only after agreeing to these additional terms.

For more detailed information, please refer to AZ Direct GmbH's terms and conditions provided within the Udacity workspace.
