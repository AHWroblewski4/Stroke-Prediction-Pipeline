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
