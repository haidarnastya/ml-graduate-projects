# Decision Trees, LASSO, and Boosting for Interpretable Regression #

## Overview ##
In this project, I explored both interpretable models and regularized regression techniques across two datasets.

The first part focused on using decision trees for a multi-label classification problem.  
The second part focused on high-dimensional regression, where I compared classical linear models, regularization techniques (Ridge and LASSO), dimensionality reduction (PCR), and gradient boosting.
---

## Part 1 — Decision Trees as Interpretable Models (Acute Inflammations Dataset) ##

## Decision tree ##
I trained a decision tree classifier on the full dataset and visualized the resulting tree structure. I explored approaches for handling multiple labels when building the tree.

### Decision rules ##
I translated the learned tree structure into a set of IF–THEN rules.

## Cost-complexity pruning ##
To improve interpretability, I applied cost-complexity pruning to find a smaller tree that retained strong predictive performance while simplifying the rule set.

---

## Part 2 — Regression with Regularization and Boosting (Communities and Crime Dataset) ##

This dataset is high-dimensional, contains missing values, and includes many potentially irrelevant predictors.

## Data Cleaning ##
- Handled missing values using imputation
- Removed non-predictive features based on dataset documentation
- Split the data into the prescribed training and test sets

## Explored feature relationships ##
- Plotted a correlation matrix to understand relationships between features
- Computed the Coefficient of Variation (CV) for each feature
- Selected the top features by CV and visualized them using scatterplots and boxplots

## Linear regression ##
I fit a standard least squares linear regression model and evaluated its test error to serve as a baseline.

## Ridge regression ##
I trained a ridge regression model with the regularization parameter selected using cross-validation and compared its performance to the baseline model.

## LASSO regression ##
I trained LASSO models with cross-validated regularization parameters:
- Using raw features
- Using standardized features

I compared:
- Test errors
- The set of variables selected by LASSO in each case

## Principal Component Regression (PCR) ##
I performed PCR, selecting the optimal number of principal components using cross-validation, and evaluated its performance on the test set.

## Gradient boosting with L1-penalized trees (XGBoost) ##
Finally, I trained a gradient boosting model using XGBoost, incorporating L1-penalized regression at each node to handle the large number of predictors.
The regularization term was selected via cross-validation.

---

## Model Comparison ##
Across all regression approaches, I compared:
- Test errors
- Feature selection behavior
- Interpretability vs. predictive power
- The impact of regularization and dimensionality reduction
---

## Data ##
The datasets used in this project come from the UCI Machine Learning Repository and are not included in this repository.
- Acute Inflammations Dataset:  
  https://archive.ics.uci.edu/ml/datasets/Acute+Inflammations

- Communities and Crime Dataset:  
  https://archive.ics.uci.edu/ml/datasets/Communities+and+Crime
