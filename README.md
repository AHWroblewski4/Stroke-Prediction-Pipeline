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

## Dataset
Source: Kaggle – Healthcare Dataset Stroke Data

Link: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

## Model Performace
| Model               | Accuracy | AUC  | Precision | Recall | Specificity | Interpretation                                   |
| ------------------- | -------- | ---- | --------- | ------ | ----------- | ------------------------------------------------ |
| Logistic Regression | 0.727     | 0.861 | 0.154      | 0.810   | 0.722        | Strong recall, interpretable model               |
| SVM                 | 0.719     | 0.861 | 0.155      | 0.845   | 0.712        | High recall, good sensitivity                    |
| GBT                 | 0.819     | 0.802 | 0.162      | 0.50   | 0.839        | Best trade-off between precision and specificity |
| MLP                 | 0.779     | 0.698 | 0.096     | 0.328   | 0.8097       | Poorest performer overall                        |

** All models achieved moderate-to-high accuracy, but precision remained low due to class imbalance


## Performace Across VMS

| **Number of VMs** | **Cores Used (8 per VM)** | **Total Runtime (min)** | **Model Training + Evaluation Time (s)** |
| ----------------- | ------------------------- | ----------------------- | ---------------------------------------- |
| 1 VM              | 8                         | 54                      | 3,113.05                                 |
| 2 VMs             | 16                        | 37                      | 2,140.14                                 |
| 3 VMs             | 24                        | 36                      | 1,999.54                                 |
| 4 VMs             | 32                        | 27                      | 1,536.06                                 |

As the number of virtual machines increased, both the total runtime and the model training time decreased. Running the Spark pipeline on multiple VMs allowed tasks to be processed in parallel, reducing computation time compared to a single-VM setup.

## Cluster Setup
* 1 Master Node
* 3 Worker Nodes
* Passwordless SSH configured between nodes
* Spark Standalone mode used with the Spark master at spark://master:7077
* Data stored and accessed via HDFS (hdfs://master:9000/user/sat3812/stroke_project/data/)

## Requirements   
* Python 3.x
* Apache Spark installed on all VMs
* PySpark, NumPy, Pandas


## Team Members
Andrea Wroblewski

Olivia Gette

