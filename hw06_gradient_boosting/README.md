# Tree-Based Methods for Imbalanced Classification (APS Failure Dataset) #

## Overview ##
In this project, I worked with a highly imbalanced industrial dataset from Scania Trucks to explore how tree-based models behave in the presence of missing data and severe class imbalance.

I compared:
- Standard Random Forests
- Random Forests with class imbalance handling
- Model trees built using XGBoost with L1-penalized logistic regression
- The effect of SMOTE oversampling

---

## Data Cleaning ##
This dataset contains substantial missing data. Instead of discarding rows, I researched and applied a data imputation technique to preserve as much information as possible.

## Feature variability ##
For each of the 170 features, I computed the Coefficient of Variation (CV) to understand which features exhibited the greatest relative variability.

## Visualized feature relationships ##
- Generated a correlation matrix across all features
- Selected the top √170 features by CV for visualization
- Created scatterplots and boxplots to explore how well these features separate the classes

## Examined class imbalance ##
I calculated the number of positive and negative samples and confirmed that the dataset is highly imbalanced, which plays a major role in model performance.

---

## Random Forest without imbalance compensation ##

I trained a standard Random Forest classifier on the dataset without addressing class imbalance.
For both training and test sets, I reported:
- Confusion matrix
- ROC curve
- AUC
- Misclassification rate
I also computed the Out-of-Bag (OOB) error and compared it to the test error.

---

## Random Forest with imbalance compensation ##

Next, I researched methods for handling class imbalance in Random Forests and applied an appropriate strategy.
I repeated the evaluation and compared performance to the uncompensated model.

---

## Model Trees with XGBoost (L1-penalized logistic regression at each node) ##

I trained model trees where each node uses a linear decision rule based on all features.

Using XGBoost with L1-penalized logistic regression at each node:
- I selected the regularization parameter via cross-validation
- Trained the model without imbalance compensation
- Estimated error using cross-validation and compared it to test error
- Reported confusion matrices, ROC curves, and AUC for training and test sets

---

## SMOTE and XGBoost ##

To further address imbalance, I applied SMOTE (Synthetic Minority Over-sampling Technique) to the training data.

I retrained the XGBoost model using the SMOTE-processed data and carefully applied cross-validation to avoid data leakage.
I compared:
- Performance before and after SMOTE
- The impact of synthetic oversampling on model behavior
- Differences in ROC, AUC, and confusion matrices

---

## Model Comparison ##
Across all approaches, I compared:
- The effect of class imbalance
- The impact of imputation and preprocessing
- Traditional tree splits vs. model tree splits
- Random Forest vs. XGBoost model trees
- The role of SMOTE in improving minority class detection

---

## Data ##
The dataset used in this project comes from the UCI Machine Learning Repository and is not included in this repository.
APS Failure at Scania Trucks Dataset:  
https://archive.ics.uci.edu/ml/datasets/APS+Failure+at+Scania+Trucks
