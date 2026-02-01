# Supervised, Semi-Supervised, Unsupervised, and Active Learning with SVMs #

## Overview ##
In this project, I explored how different learning paradigms perform on the same classification task:
- Supervised learning
- Semi-supervised (self-training)
- Unsupervised learning used as a classifier
- Active vs. passive learning strategies
Using Support Vector Machines and clustering methods, I compared how access to labels, data selection strategy, and learning framework influence model performance.
All evaluations were performed using Monte Carlo simulation.

---

## Part 1 — Learning Paradigms on the Breast Cancer Wisconsin Dataset ##
This dataset contains 30 numeric features describing cell nuclei from breast cancer biopsies, labeled as benign or malignant.

## Monte Carlo evaluation ##
For each method below, I:
- Repeated the entire experiment 30 times
- Used stratified splits so 20% of each class formed the test set
- Reported average accuracy, precision, recall, F1-score, and AUC across runs
- Plotted ROC curves and confusion matrices for representative runs

---

## Supervised Learning — L1-penalized SVM ##
- Normalized the data
- Used 5-fold cross-validation to select the penalty parameter
- Trained an L1-regularized SVM on the full labeled training set
- Evaluated performance on both training and test sets

---

## Semi-Supervised Learning — Self-Training SVM ##
- Began with only 50% of training labels
- Trained an L1-penalized SVM on the labeled subset
- Iteratively:
  - Found the unlabeled point farthest from the decision boundary
  - Assigned it the predicted label
  - Retrained the SVM
- Continued until all data were labeled
- Evaluated the final classifier on the test set
---

## Unsupervised Learning as a Classifier — K-Means ##
- Applied K-Means with k = 2 to the unlabeled training data
- Determined cluster labels using majority voting from points closest to cluster centers
- Treated clusters as predicted classes
- Evaluated performance on both training and test data
- Repeated with multiple random initializations to avoid local minima

---

## Spectral Clustering ##
- Repeated the clustering experiment using spectral clustering with an RBF kernel
- Labeled clusters using majority voting
- Evaluated performance as a classifier
- Compared results to K-Means

---

## Part 2 — Active vs. Passive Learning on the Banknote Dataset ##
This dataset contains features extracted from banknote images for authentication.

## Setup ##
- Randomly selected 472 samples as the test set
- Used the remaining 900 as the training pool
- Repeated experiments 50 times for Monte Carlo evaluation

---

## Passive Learning ##
- Started with 10 random training samples
- Trained an L1-penalized linear SVM
- Incrementally added 10 random samples at a time
- Recorded test error for each model (10 → 900 samples)
- Produced a learning curve

---

## Active Learning ##
- Started with 10 random samples
- Trained an SVM
- Selected the 10 training points closest to the decision boundary
- Added them to the training pool
- Repeated until all data were used
- Recorded test error at each step

---

## Learning curve comparison ##
By averaging results across 50 runs, I plotted Test error vs. number of training instances for passive learning and active learning.

---

## Dataset ##
Datasets used in this project come from the UCI Machine Learning Repository and are not included in this repository.

Breast Cancer Wisconsin (Diagnostic) Dataset:  
https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29

Banknote Authentication Dataset:  
https://archive.ics.uci.edu/ml/datasets/banknote+authentication
