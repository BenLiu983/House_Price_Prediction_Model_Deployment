# House Price Prediction Model Development and Deployment


# Introduction

The aim of the project is to build a machine learning model to predict the sale price of houses based on different explanatory variables describing aspects of residential houses. Predicting house price is useful to identify fruitful investments, or to determine whether the price advertised for a house is over or under-estimated. I will also serve the model via REST API, deploy the model to AWS using Docker.

# Metrics

The metrics to evaluate model performance would be the mean squared error (mse), the root of the mean squared error (rmse), and r square.

# Section 1 Model Development

1.1 Exploratroy Data Analysis (EDA)

The house price dataset contains 1460 rows (houses), and 81 columns (variables/features).

![data](https://user-images.githubusercontent.com/64850893/103929340-239d9a80-50eb-11eb-8bea-3a9d1116fd4f.jpg)


**Analyse the dataset to identify:**

1. Missing values
2. Numerical variables
3. Distribution of the numerical variables
4. Outliers
5. Categorical variables
6. Cardinality of the categorical variables
7. Potential relationship between the variables and the target: SalePrice

1.2 Feature Engineering

Pre-process the variables of the House Price Dataset:

1. Missing values: imputation
2. Temporal variables: manipulation
3. Non-Gaussian distributed variables: tranformation
4. Categorical variables: remove rare labels, convert strings to numbers
5. Standardise the values of the variables to the same range

1.3 Feature Selection

The desired features include:'MSSubClass', 'MSZoning', 'Neighborhood', 'OverallQual', 'OverallCond',
       'YearRemodAdd', 'RoofStyle', 'MasVnrType', 'BsmtQual', 'BsmtExposure',
       'HeatingQC', 'CentralAir', '1stFlrSF', 'GrLivArea', 'BsmtFullBath',
       'KitchenQual', 'Fireplaces', 'FireplaceQu', 'GarageType',
       'GarageFinish', 'GarageCars', 'PavedDrive'.

       
1.4 Modeling 
I will the regularized linear regression (LASSO) for the modeling.
The MSE, rmse and r square of the test set and is 1405259552, 37486 and 0.796 respectively.

![model](https://user-images.githubusercontent.com/64850893/103930484-d3273c80-50ec-11eb-9b7b-c537d84624d2.jpg)

From the above metrics and plots, the model does a pretty good job at estimating house prices.

The importance of features is as follows:

![feature_imp](https://user-images.githubusercontent.com/64850893/103930672-1e414f80-50ed-11eb-9df7-05bc77369c4e.jpg)

1.5 Summary 

Summarize the key pieces of code, which is necessary to take forward for this project, in order to put the model in production.


# Section 2 Production Code 

2.1 Scikit-learn pipeline

  
# Section 3 Model Deployment

3.1 Serve the model via REST API

3.2 Run with Docker

3.3 Deploy the model to AWS

