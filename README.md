
## Overview

This Python code is developed to analyze and predict UFC fight winners based on historical data. It involves data preprocessing, exploratory data analysis, feature engineering, and model training with RandomForestClassifier and XGBoost.

## Libraries

The following libraries are imported:

- pandas
- numpy
- matplotlib.pyplot
- altair
- seaborn
- sklearn (LabelEncoder, train_test_split, RandomForestClassifier, cross_val_score, SimpleImputer)
- xgboost (XGBClassifier)
- sklearn.metrics (classification_report, confusion_matrix, accuracy_score)

## Data Preparation

- Read the data from 'data/data.csv' and make a copy of the original dataframe
- Add a 'YearOfGame' column to the dataframe
- Count the number of null values in the dataframe
- Impute missing values using median and most frequent strategies
- Impute mean values for columns with null values
- Drop the 'Referee' column from the dataframe

## Exploratory Data Analysis

- Calculate year-wise games and visualize them as a bar chart
- Calculate games in each weight class and display the count
- Calculate winners of each game and visualize them as an area chart

## Feature Engineering

- Fill null values in 'B_Stance', 'R_Stance', and 'weight_class' columns with mode
- Label encode 'R_Stance', 'B_Stance', 'R_fighter', 'B_fighter', and 'weight_class' columns
- Drop unrelated columns from the dataframe
- Label encode the target variable 'Winner'

## Model Training and Evaluation

### RandomForestClassifier

1. Split the data into training and testing sets
2. Train and evaluate a RandomForestClassifier model
   - Calculate test accuracy and cross-validation accuracy
   - Display a confusion matrix
   - Display the top 10 most important features

### XGBoost

1. Train and evaluate an XGBoost model
   - Calculate test accuracy and cross-validation accuracy

### Model Comparison

1. Display a table with accuracy scores of RandomForest and XGBoost models
2. Calculate the T-statistic for RandomForest and XGBoost models
   - Compute the sample mean and sample standard deviation of the difference in accuracy between the two models
   - Calculate the T-statistic using the sample mean, sample standard deviation, and the number of cross-validation folds

By comparing the performance of RandomForestClassifier and XGBoost models using accuracy scores and T-statistic, you can determine which model performs better on the given dataset and choose the appropriate model for predicting UFC fight winners.
