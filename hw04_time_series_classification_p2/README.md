# Time Series Classification – Binary and Multiclass Classification (AReM Dataset) PART 2 #

## Overview ##
In this project, I extended the previous time series feature extraction work 
(from Part 1) to perform both binary and multiclass classification of human 
activities. The goal was to investigate how different classification methods handle
time-domain features derived from sensor signals and to evaluate model
performance in both binary and multi-class settings.

## Binary Classification ##
I first focused on distinguishing bending activities from other activities
using logistic regression. Key steps included:

- Visualizing features from selected time series to understand class separation.
- Splitting each time series into multiple segments to increase feature resolution.
- Applying logistic regression with both p-value-based feature selection
  and L1-penalized regularization.
- Using cross-validation and stratified sampling to handle class imbalance.
- Evaluating model performance with confusion matrices, ROC curves, and AUC.

## Multiclass Classification ##
I then extended the analysis to classify all activity types:

- Built an L1-penalized multinomial logistic regression model to predict
  multiple activity classes.
- Compared results with Naïve Bayes classifiers using both Gaussian and
  Multinomial priors.
- Evaluated performance with multiclass confusion matrices and ROC analysis
  where appropriate.

## Data ##
The dataset comes from the UCI Machine Learning Repository and is not
included in this repository. Download the AReM data from: 
https://archive.ics.uci.edu/ml/datasets/Activity+Recognition+system+based+on+Multisensor+data+fusion+\%28AReM\%29
