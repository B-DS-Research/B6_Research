# RMDS Hackathon – Seasonal Vaccine Prediction

## Project Overview

This project was developed as part of the Research Methods for Data Science (RMDS) Hackathon at the University of Hertfordshire. The aim of the project is to predict whether an individual received the seasonal influenza (flu) vaccine using demographic, behavioural, medical, socioeconomic, and opinion-based survey data.

The task is formulated as a binary classification problem, where machine learning models are trained to classify respondents based on their likelihood of receiving the seasonal vaccine.

## Target Variable

The target variable for this project is **seasonal_vaccine**, which represents whether a respondent received the seasonal flu vaccine:

* **0** – Respondent did not receive the seasonal vaccine
* **1** – Respondent received the seasonal vaccine

## Identifier Column

The dataset includes a unique identifier column called **respondent_id**. This column is used solely for identifying respondents and generating submission files. It is excluded from the feature set during model training to prevent data leakage and ensure unbiased predictions.

## Dataset Summary

The project utilizes two datasets:

* **Training Dataset:** `dataset_A_training.csv`
* **Testing Dataset:** `dataset_A_testing.csv`

### Dataset Statistics

| Dataset      | Number of Records |
| ------------ | ----------------- |
| Training Set | 4,756             |
| Testing Set  | 4,749             |

### Submission Format

The final prediction file contains the following columns:

* `respondent_id`
* `seasonal_vaccine`
* 
## Project Workflow

1. Data Loading
2. Dataset Overview
3. Exploratory Data Analysis (EDA)
4. Missing Value Analysis
5. Target Distribution Analysis
6. Numerical Feature Analysis
7. Categorical Feature Analysis
8. Correlation Analysis
9. Feature-Target Relationship Analysis
10. Data Leakage Assessment
11. Data Preprocessing Pipeline
12. Model Training
13. Model Comparison
14. Cross-Validation
15. Hyperparameter Tuning
16. Explainable AI (XAI)
17. Submission File Generation
18. Critical Analysis and Documentation

This structured workflow ensures that the dataset is thoroughly explored, appropriately preprocessed, and evaluated using multiple machine learning techniques.

## Exploratory Data Analysis (EDA)

Exploratory Data Analysis (EDA) was conducted to understand the structure, quality, and characteristics of the dataset before model development. This step helped identify patterns, data quality issues, and relationships between features and the target variable.

The EDA included:

- Summary Statistics
- Missing Value Analysis
- Missing Value Matrix
- Target Class Distribution
- Numerical Feature Histograms
- Numerical Feature Boxplots
- Categorical Frequency Plots
- Correlation Heatmap
- Feature-Target Relationship Plots

These analyses provided valuable insights that guided data preprocessing, feature engineering, and model selection decisions.

---

## Missing Value Handling

Several variables contained missing values, particularly healthcare-related and socioeconomic features. To preserve valuable information and avoid reducing the dataset size, missing values were handled using imputation rather than removing incomplete records.

The preprocessing strategy was:

| Feature Type | Missing Value Strategy | Transformation |
|-------------|----------------------|---------------|
| Numerical Features | Median Imputation | StandardScaler |
| Categorical Features | Most Frequent Imputation | OneHotEncoder |

Median imputation was chosen for numerical features because it is robust to outliers, while one-hot encoding was used to convert categorical variables into a machine-learning-friendly format without introducing artificial ordinal relationships.
