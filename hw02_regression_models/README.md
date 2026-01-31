# Regression Modeling and Evaluation (Combined Cycle Power Plant Dataset)

## Overview ##
In this project, I built and evaluated regression models to predict the hourly
electrical energy output of a power plant using environmental measurements
such as temperature, pressure, humidity, and exhaust vacuum.

The goal was to explore how different regression approaches capture relationships
between predictors and response, including linear, nonlinear, interaction-based,
and instance-based methods.

## Exploratory Data Analysis ##
I began with an exploratory analysis, including pairwise scatterplots and summary 
statistics to examine relationships between predictors and the response variable.

## Simple and Multiple Linear Regression ##
I fit individual linear regression models for each predictor and compared them
to a full multiple regression model using all variables. This helped reveal how
predictors behave differently in isolation versus together.

## Coefficients ##
I compared coefficients from simple linear regression to those from multiple
regression to understand how correlation between predictors affects
model interpretation.

## Nonlinear Relationships ##
I extended the regression models to include polynomial terms and evaluated 
whether higher-order relationships improved model fit.

## Interaction Effects ##
I expanded the model to include pairwise interaction terms between predictors
and assessed which interactions were statistically significant.

## Model Refinement and Evaluation ##
Using a 70/30 train–test split, I refined regression models by removing
insignificant terms based on p-values and compared performance using
mean squared error on both training and test sets.

## KNN Regression ##
I implemented K-Nearest Neighbors regression using both normalized and raw
features, selected the optimal k, and compared its performance to the best
linear regression model.

## Data ##
The dataset comes from the UCI Machine Learning Repository and is not
included in this repository. Download the Combined Cycle Power Plant data1 from:
https://archive.ics.uci.edu/ml/datasets/Combined+Cycle+Power+Plant
