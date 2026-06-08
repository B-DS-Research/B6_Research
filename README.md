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

## Models Trained

Multiple machine learning models were trained and compared to identify the most effective approach for predicting seasonal vaccine uptake. The selected models range from interpretable baseline algorithms to advanced ensemble and boosting techniques.

The following models were trained and evaluated:

| Model | Purpose |
|---------|---------|
| Logistic Regression | Interpretable baseline model |
| Decision Tree | Simple nonlinear tree model |
| Random Forest | Robust ensemble baseline |
| Extra Trees | Randomised tree ensemble |
| Gradient Boosting | Sequential boosting model |
| XGBoost | Advanced gradient boosting model |
| LightGBM | Fast gradient boosting model |
| CatBoost | Boosting model suitable for categorical-style data |

A total of **8 machine learning models** were trained and compared to determine the best-performing approach for this classification task.

---

## Evaluation Metrics

The trained models were evaluated using multiple classification metrics to assess their predictive performance and reliability.

The evaluation metrics included:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

Particular emphasis was placed on **ROC-AUC** and **F1-Score**, as these metrics provide a more comprehensive assessment of binary classification performance. ROC-AUC measures the model's ability to distinguish between vaccinated and non-vaccinated respondents, while F1-Score balances precision and recall.

---

## Cross-Validation

Stratified Cross-Validation was applied to the top-performing models to obtain a more reliable estimate of model performance and generalisation capability.

The validation process ensured that the class distribution remained consistent across different folds, reducing the risk of biased evaluation results.

By evaluating models across multiple data splits rather than relying on a single train-validation split, cross-validation provided a more robust assessment of model stability and predictive performance.

## Hyperparameter Tuning

To further improve model performance, the XGBoost classifier was optimized using **RandomizedSearchCV**. Hyperparameter tuning was performed to identify the best combination of parameters and enhance the model's ability to generalize to unseen data.

The tuning process evaluated the following parameters:

- n_estimators
- max_depth
- learning_rate
- subsample
- colsample_bytree

By optimizing these parameters, the model achieved a better balance between predictive performance and overfitting, resulting in improved generalization on the validation data.

## Explainable AI (XAI)

Explainable AI (XAI) techniques were applied to interpret model behaviour and provide greater transparency into the prediction process. These methods helped identify the most influential features and supported the critical analysis of model performance.

The project included:

- Permutation Feature Importance
- SHAP (SHapley Additive exPlanations) Analysis

Permutation Feature Importance was used to identify the features that had the greatest impact on model performance. SHAP analysis was applied to explain how individual features contributed to model predictions and to provide insights into the factors influencing seasonal vaccine uptake.

## Critical Analysis

The project focused not only on model performance but also on understanding the reasoning behind key methodological decisions. A critical analysis was conducted to evaluate the strengths, limitations, and practical implications of the modelling approach.

The analysis included:

- Why missing values were imputed instead of removed
- Why ROC-AUC and F1-Score were selected as key evaluation metrics
- Why ensemble and boosting models performed strongly
- Why linear models may have limitations for this dataset
- How preprocessing decisions influenced model performance
- What the most important features reveal about vaccine uptake
- Model limitations and potential sources of bias
- Opportunities for future improvements

This analysis provided a deeper understanding of the modelling process and helped place the results within a broader data science context.

---

## Output Files

The notebook automatically generates several output folders and files to store visualizations, results, submissions, and project documentation.

The generated project structure includes:

```text
figures/         Saved EDA, performance, and XAI visualizations
outputs/         Summary tables, model results, and analysis reports
submissions/     Final prediction CSV files
documentation/   Team notes and project documentation
README.md        Project documentation

## Important Plots Generated

The project generates a variety of visualizations to support data exploration, model evaluation, and model interpretability. These plots help identify patterns, assess performance, and explain model predictions.

The generated plots include:

- Missing Value Percentages
- Missing Value Matrix
- Target Distribution
- Numerical Feature Distributions
- Outlier Boxplots
- Categorical Feature Distributions
- Correlation Heatmap
- Feature-Target Relationship Plots
- Model Comparison by ROC-AUC
- Model Comparison by F1-Score
- Confusion Matrix
- ROC Curve
- Permutation Feature Importance
- SHAP Summary Plot

These visualizations provide valuable insights into the dataset, model behaviour, and prediction outcomes.

---

## Summary Tables Generated

The notebook also generates presentation-ready summary tables that document key findings and modelling results throughout the project.

The generated tables include:

- Dataset Overview Table
- Missing Values Summary Table
- Target Balance Table
- Feature Type Summary Table
- Correlation Summary Table
- Preprocessing Decisions Table
- Models Trained Table
- Model Performance Table
- Cross-Validation Results Table
- Tuned Model Results Table
- Feature Importance Table
- Submission Summary Table

These tables provide a structured overview of the dataset, preprocessing decisions, model performance, and final project outputs.
