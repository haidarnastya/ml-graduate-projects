# Binary Classification with K-Nearest Neighbors (Vertebral Column Dataset) #

## Overview ##
In this project, I built a binary classification model to distinguish between
normal and abnormal spinal conditions using six biomechanical measurements
of the pelvis and lumbar spine.

The goal was to implement K-Nearest Neighbors (KNN) and explore
how model behavior changes with different choices of distance metrics,
training set sizes, and voting strategies.

## Explored the data ##
I started with exploratory visualizations (scatterplots and boxplots) to see
how well the two classes separated across features and see the distribution of
the dataset.

## KNN classifier ##
I implemented KNN using Euclidean distance and evaluated performance across
a wide range of values for k. The optimal value was chosen based on test error.

## Evaluated model performance ##
For the selected model, I computed a confusion matrix along with precision,
recall, and F1-score.

## Analyzed learning behavior ##
I generated learning curves by varying the number of training samples and 
re-selecting the best k for each case.

## Experimented with distance metrics ##
I replaced Euclidean distance with:
- Manhattan (Minkowski p=1)
- General Minkowski distances
- Chebyshev distance
- Mahalanobis distance
and compared how each affected classification performance.

## Tried weighted voting ##
Finally, I implemented a weighted version of KNN where closer neighbors have
greater weight/influence and compared results across distance metrics.

## Data
The dataset comes from the UCI Machine Learning Repository and is not
included in this repository. Download the Vertebral Column Data Set 
from: https://archive.ics.uci.edu/ml/datasets/Vertebral+Column
