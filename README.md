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

The objective is to predict the seasonal vaccine status for each respondent in the testing dataset and generate submission files in the required format.

