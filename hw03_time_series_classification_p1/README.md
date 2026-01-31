# Time Series Classification – Feature Extraction (AReM Dataset) PART 1 #

## Overview ##
In this project, I worked on classifying activities using time series
collected from a wireless sensor network. Each instance in the dataset contains
six sensor signals capturing movement over time.

The goal was to extract meaningful time-domain features from the raw sensor
data and identify which features are most informative for classification.

## Exploratory Data Analysis ##
I began with an exploratory analysis of the time series to understand
their structure and variability. This included examining the range, mean,
median, and standard deviation of the signals for different activity instances.

## Feature Extraction ##
I extracted key time-domain features for each of the six time series in every
instance, including:
- Minimum
- Maximum
- Mean
- Median
- Standard deviation
- First quartile
- Third quartile

## Variability Analysis  ##
I estimated the standard deviation of each feature and used bootstrap
sampling to construct 90% confidence intervals. 

## Feature Selection ##
Based on the analysis and feature importance, I selected the three most
informative features to use for downstream classification tasks.

## Data  ##
The dataset comes from the UCI Machine Learning Repository and is not
included in this repository. Download the AReM data from: 
https://archive.ics.uci.edu/ml/datasets/Activity+Recognition+system+based+on+Multisensor+data+fusion+\%28AReM\%29 
