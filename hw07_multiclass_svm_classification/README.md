# Multi-Label Classification and Clustering with SVMs and K-Means (Anuran Calls Dataset) #

## Overview ##
In this project, I worked with a multi-class, multi-label dataset of frog calls represented by MFCC features.
Each recording is labeled at three taxonomic levels:
- Family
- Genus
- Species

I explored both supervised and unsupervised learning approaches to understand how well these labels can be recovered from audio features.

---

## Data Preparation ##
- Randomly split 70% of the data as training and 30% as test data for supervised learning
- Verified that features were already normalized
  
---

## Evaluated multi-label performance ##
Before modeling, I researched and implemented appropriate evaluation metrics for multi-label classification:
- Exact match score
- Hamming score
- Hamming loss
These metrics were used throughout the project to assess classifier performance.

---

## SVM classifiers with Gaussian kernels ##
For each label (Family, Genus, Species), I trained an SVM using:
- One-vs-all strategy
- Gaussian (RBF) kernels
- 10-fold cross-validation to tune:
  - Penalty parameter
  - Kernel width
I compared performance using both raw and standardized features.

---

## L1-penalized SVMs ##
Next, I trained L1-regularized SVMs with linear kernels:
- Standardized features
- Cross-validation to select the penalty parameter
- Compared results to the Gaussian kernel SVMs in terms of sparsity and performance

---

## SMOTE for class imbalance ##
Because several classes were underrepresented, I applied SMOTE to the training data and retrained the L1-penalized SVMs.
I compared:
- Performance before and after oversampling
- The effect of imbalance correction on Hamming metrics
---

## K-Means clustering (unsupervised learning) ##
I then explored how well unsupervised clustering could recover the biological label structure.

### Number of clusters ##
- Ran K-Means for k = 1 to 50
- Selected the optimal k using clustering quality metrics (e.g., silhouette score)

### Cluster Assignment ##
For each cluster, I determined the majority:
- Family
- Genus
- Species
This produced a predicted label triplet for every cluster.

---

## Evaluating clustering performance ##
Using the true labels and cluster-derived labels, I computed:
- Average Hamming distance
- Hamming score
- Hamming loss
This process was repeated 50 times using Monte Carlo simulation, and I reported the mean and standard deviation of the results.

---

## Model Comparison ##
This project highlights:
- Differences between Gaussian and L1-penalized SVMs
- The impact of class imbalance in multi-label classification
- The usefulness of SMOTE in high-dimensional settings
- How well unsupervised clustering can approximate structured biological labels

---

## Data ##
The dataset used in this project comes from the UCI Machine Learning Repository and is not included in this repository.
Anuran Calls (MFCCs) Dataset:  
https://archive.ics.uci.edu/ml/datasets/Anuran+Calls+%28MFCCs%29
