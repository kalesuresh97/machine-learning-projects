# Warehouse Processing Time Prediction


## 1. Project Overview

This project develops a Machine Learning model to predict the processing time required for warehouse orders.

The objective is to use order characteristics and warehouse operational factors to estimate order processing time and support better operational planning.

## 2. Business Problem

Warehouse order processing time can vary depending on factors such as:

- Number of items in an order
- Total quantity
- Order weight
- Picking distance
- Number of pickers
- Picker experience
- Warehouse congestion
- Order priority
- Shift
- Equipment type

Accurately estimating processing time can help warehouse operations with workload planning, resource allocation, and scheduling.

## 3. Objective

Build and evaluate a Linear Regression model that predicts:

Order Processing Time (minutes)

The model is evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R²
- Adjusted R²

## 4. Machine Learning Approach

The project follows a standard supervised machine learning workflow:

1. Data loading and understanding
2. Exploratory Data Analysis (EDA)
3. Numerical and categorical feature analysis
4. Data preprocessing
5. Train-test split
6. Linear Regression baseline model and evaluation
7. Residual analysis
8. Multicollinearity analysis using VIF
9. Cross-validation
10. Ridge and Lasso regularization
11. Feature selection
12. Final Linear Regression model
13. Evaluation on unseen test data
14. Business interpretation

## 5. Feature Selection

Feature selection was evaluated using model performance, correlation analysis, multicollinearity analysis, and cross-validation.
Features that did not provide useful predictive value were removed.

The final model excluded:

- number_of_skus
- temperature_c
- day_of_week columns

The remaining features were retained based on their contribution to model performance.

## 6. Model

Linear Regression

The final model was selected after evaluating the baseline model, cross-validation performance, Ridge and Lasso regularization, and feature-selection experiments.

## 7. Model Performance

The final model was evaluated on an unseen test dataset.

|Metric| Training |Testing |
|------:---:--------:---------
| MAE  | 5.63 min | 5.57 min|
| RMSE | 7.08 min | 7.02 min|
| R²   |    0.733 | 0.737   |
| Adjusted R² | — | 0.735   |

### Interpretation

The model achieved a test R² of approximately 0.737, meaning it explains around 73.7% of the variation in warehouse processing time on unseen data.

The test MAE of approximately 5.57 minutes means that the model's predictions differ from the actual processing time by about 5.6 minutes on average.

The training and testing metrics are very close, indicating good model stability and no significant evidence of overfitting.

## 8. Business Value

The model can potentially support:

- Estimation of expected processing time for incoming orders
- Warehouse workload planning
- Picker/resource allocation
- Operational scheduling
- Identification of orders that may require more processing time

## 9. Limitations

The model does not explain all variation in processing time. Approximately 26% of the variation remains unexplained by the current feature set.

Additional operational variables and more advanced nonlinear models could potentially improve predictive performance.


## 10. Project Files

1.Requirement.txt
2.README.md
3.Data:
   -warehouse_orders_raw.csv
4.Notebook:
  -01_EDA.ipynb
  -02_Preprocessing.ipynb
  -03_Linear_Regression.ipynb
5.linear_regression_model.pkl

    
    
    
    