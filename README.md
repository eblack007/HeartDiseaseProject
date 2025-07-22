# Heart Disease Prediction Project

## Project Overview

This project is an end-to-end machine learning workflow to predict the likelihood of a patient having heart disease based on various medical attributes. The process includes data cleaning, comprehensive exploratory data analysis (EDA), feature engineering, model training, and hyperparameter tuning to achieve the best possible performance.

The best model developed was a **Tuned Random Forest**, which achieved an **accuracy of 87%** on the test set.

## Dataset

The project uses the "Heart Failure Prediction" dataset from Kaggle available at https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/data. The raw data is located in `data/raw/heart.csv` and contains 12 columns, including patient demographics and clinical measurements. The target variable is `HeartDisease`, where `1` indicates the presence of heart disease and `0` indicates its absence.

## Project Workflow

The project is structured into a series of Jupyter notebooks that follow a logical progression:

1.  **`01_eda_and_cleaning.ipynb`**:
    * Loads the raw dataset.
    * Performs initial data inspection and cleaning, including handling erroneous zero values and outliers in columns like `RestingBP` and `Cholesterol`.
    * Conducts detailed univariate and bivariate analysis to understand feature distributions and their relationship with the target variable. The EDA identified strong predictors like `Oldpeak`, `MaxHR`, `Age`, `ST_Slope`, and `ChestPainType`.

2.  **`02_feature_engineering.ipynb`**:
    * Encodes all categorical features into a numerical format suitable for modeling.
    * Uses label encoding for binary features and one-hot encoding for multi-category features.
    * Saves the processed data to `data/processed/heart_encoded.csv`.

3.  **`03_model_building.ipynb`**:
    * Loads the processed data and applies feature scaling using `StandardScaler`.
    * Splits the data into training and testing sets.
    * Builds and evaluates a baseline Logistic Regression model (86% accuracy) and a more complex Random Forest model (87% accuracy).
    * Performs hyperparameter tuning using `GridSearchCV` on the Random Forest model, which confirmed the 87% accuracy and suggested the model is feature-limited.

4. **'04_results_analysis.ipynb'**:
* Displays the dataframe containing results from each iteration