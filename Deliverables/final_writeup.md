# Sepsis Classification

## Background

For this project, I decided to focus on developing a classification model to help predict whether or not a patient will develop Sepsis, based on a number of features. I built KNN, Logistic Regression, and Random Forest models, and focused on the f_beta (b=2) metric, as I wanted to place emphasis on recall, but also take into account the precision of my model. I chose the Random Forest model as my final model, as it had the highest ROC-AUC score, as well as f_beta 2 score, after some hyperparameter tuning.

## Design

Sepsis is a deadly, but preventable and treatable infection that often occurs in people who are hospitalized, or who have recently been hospitalized. According to the CDC, every year, around 1.7 million Americans develop sepsis, with around 270,000 people dying. Furthermore, Sepsis is the leading cause of death in hospitals, accounting for between 1/3rd and 1/5th of hospital deaths.

Building a classification model that can predict if a person will develop sepsis can help medical professionals take adequate and timely preventative measures to aid patients in the recovery from sepsis, and to decrease sepsis related deaths in hospitals.

## Data

The data I obtained for this classification project was a [Kaggle dataset](https://www.kaggle.com/maxskoryk/datasepsis). The original dataset has 36,302 rows, and 41 total columns.

The data consists of measurements of a patient, six days prior to Sepsis testing.

The data itself is highly imbalanced, with only around 2% positive Sepsis rows, and 98% negative. To help mitigate the effects of this imbalance, I did some resampling, using Random Oversampling to get an even 50-50 ratio of data. This ratio may not be the most ideal, as it duplicates the same 2% of rows many times.

Furthermore, there is a significant number of null or missing data in the set. I am not sure if they are missing simply because some measurements are not always required across all patients, or if they have simply been lost. Therefore, for now, I've chosen to find a combination of columns and rows without nulls, to end with about 16,000 data points.

In the future, I would like to use imputing methods to impute missing data, so the dataset can be larger to build a more robust model.

## Tools / Algorithms
Metrics: ROC-AUC and f-beta:
1. Baseline Random Forest model AUC: 0.808
2. Baseline Random Forest model F-Beta (b=2) score: 0.253
3. Random Forest model F-Beta (b=2) score after some hyperparameter tuning: 0.287

Models:
* KNN
* Logistic Regression
* Random Forest

Tools:
* Confusion Matrices
* Pandas & NumPy
* Sklearn
* Matplotlib & Seaborn
* RandomizedSearchCV - hyperparameter tuning

## Feature Importance:
![feature_importances](https://github.com/Jason-HKim/Classification_Project/blob/master/Visualizations/feature_importances.png)
