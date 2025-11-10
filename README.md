# Stroke Prediction Pipeline Using Spark-Based Machine Learning

## Background
Stroke is one of the leading causes of death and disability worldwide. Predicting a patient’s stroke risk using demographic and clinical features can help healthcare professionals identify high-risk patients early and take preventive action.

This project implements a Spark-based classification pipeline to predict stroke outcomes from a mix of demographic and health-related features. Using distributed computing across one master and multiple worker nodes, the pipeline efficiently performs preprocessing, feature encoding, model training, and evaluation.

## Features
* Data Preprocessing
* Implemented using PySpark for distributed processing
* Cleaned and standardized column names
* Missing numeric values imputed using the median
* One-hot encoding applied to categorical variables
* Features assembled and scaled using VectorAssembler and StandardScaler

## Machine Learning Models
* Logistic Regression
* Support Vector Machine (SVC)
* Gradient-Boosted Trees (GBT)
* Multilayer Perceptron (MLP)

** All models were trained and evaluated on an 80/20 train-test split using 3-fold cross-validation.


## Model Performace
| Model               | Accuracy | AUC  | Precision | Recall | Specificity | Interpretation                                   |
| ------------------- | -------- | ---- | --------- | ------ | ----------- | ------------------------------------------------ |
| Logistic Regression | 0.78     | 0.81 | 0.15      | 0.81   | 0.79        | Strong recall, interpretable model               |
| SVM                 | 0.76     | 0.80 | 0.16      | 0.85   | 0.75        | High recall, good sensitivity                    |
| GBT                 | 0.82     | 0.84 | 0.16      | 0.68   | 0.84        | Best trade-off between precision and specificity |
| MLP                 | 0.72     | 0.69 | 0.10      | 0.33   | 0.70        | Poorest performer overall                        |

** All models achieved moderate-to-high accuracy, but precision remained low due to class imbalance
