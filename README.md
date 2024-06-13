# Cirrhosis Patient Outcomes Prediction

## Overview

This project employs machine learning methods to predict the outcomes of cirrhosis patients using publicly available data from a Mayo Clinic study. The outcomes are classified into three categories: survival, survival with a liver transplant, and death. Various imputation methods for handling missing data and techniques for balancing the classes are explored. The performance of different machine learning models is evaluated, with the Random Forest model emerging as the best performer.

## Table of Contents

- [Background](#background)
- [Data](#data)
- [Imputation Methods](#imputation-methods)
- [Handling Imbalanced Classes](#handling-imbalanced-classes)
- [Model Selection and Tuning](#model-selection-and-tuning)
- [Results](#results)
- [Usage](#usage)
- [Contributors](#contributors)
- [References](#references)

## Background

The task is to predict the outcomes of cirrhosis patients from a study conducted by the Mayo Clinic between 1974 and 1984. The aim is to develop a machine learning model to assist medical professionals in directing care and understanding the associations between clinical features and patient outcomes.

## Data

The dataset comprises clinically relevant features recorded for each patient, including:
- Drug
- Age
- Sex
- Ascites
- Hepatomegaly
- Spiders
- Edema
- Bilirubin
- Cholesterol
- Copper
- Alkaline Phosphate (Alk Phos)
- SGOT
- Triglycerides
- Platelets
- Prothrombin
- Stage

These features are used to predict patient outcomes classified as:
1. Survival (C)
2. Survival with a liver transplant (CL)
3. Death (D)

## Imputation Methods

Given the likelihood of missing values in clinical settings, three imputation methods are compared:
1. **Simple Imputation:** Replaces missing values with the mean of the relevant feature.
2. **K-Nearest Neighbors (KNN) Imputation:** Replaces missing values based on the mean values of the nearest neighbors.
3. **Iterative Imputation:** Sequentially models each feature on all others and derives new values from model predictions.

## Handling Imbalanced Classes

Due to the imbalance in the dataset (62.8% C, 3.5% CL, 33.7% D), over-sampling and under-sampling methods are used:
- **Random Over-Sampling:** Adds instances to the minority class.
- **Random Under-Sampling:** Removes instances from the majority class.
- **SMOTE (Synthetic Minority Over-sampling Technique):** Creates new instances based on nearest neighbors.
- **ENN (Edited Nearest Neighbors):** Removes observations with differing nearest neighbors.

## Model Selection and Tuning

Several models were evaluated, including Support Vector Machine (SVM), Decision Tree, and Random Forest. The models were assessed using log loss as the primary performance metric. The Random Forest model, with specific tuning parameters, outperformed others, achieving the best results.

## Results

The Random Forest model achieved:
- Log Loss: 0.52
- Accuracy: 81%
- Precision, Recall, and F1-Score for each class are detailed in the report.

Despite the overall good performance, challenges remain in correctly predicting the CL class.

## Usage

To use this project:
1. Clone the repository: `git clone https://github.com/your-username/cirrhosis-prediction.git`
2. Install the required libraries: `pip install -r requirements.txt`
3. Run the data preprocessing and model training scripts: `python preprocess.py` and `python train_model.py`

## References

1. Mayo Clinic Study on Primary Biliary Cirrhosis
2. scikit-learn library for imputation methods
3. imbalanced-learn library for handling class imbalance
4. Optuna for hyperparameter tuning

For more detailed information, please refer to the project report.

---

