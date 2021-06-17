---
layout: post
title:      "An Outline for Building Machine Learning Models"
date:       2021-06-17 18:57:47 +0000
permalink:  an_outline_for_building_machine_learning_models
---


Taking on a machine learning project has a sequence of steps that is often an iterative process. This post outlines the steps of the Cross-Industry Standard Process for Data Mining (CRISP-DM), which has six phases: Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, and Deployment.

Business Understanding

What is the ultimate goal of this project. What business question are you trying to answer? A clear objective is crucial to any project. Starting without one will often lead to much wasted effort and time.

Data Understanding

Looking through the data you have and understanding it in its raw state is an important first step. It's also one of the most fun parts of the project for me. This data is a new landscape, waiting to be explored, and there is probably something unexpected that you will find.

Common techniques in this phase are running the .head(), .info(), .describe() methods on the dataframe. Scatterplots are also useful snapshots of the dataset. Boxplots can identify outliers, and histograms can show bimodal data.

This exploration should be done with a mind toward  the preprocessing phase. Are there missing values? Are there columns that are highly correlated that you can drop to streamline your feature set? Are continuous variables normally distributed?

What kind of model will you build? The answer to this will be a combination of the project goals and the data you have. Is this data suited to linear regression? Is this a binary classification problem? The model requirements will dictate certain data processing. A binary classification model will need to address class imbalance. A linear regression model will need to demonstrate that the assumptions for linear regression are met.

Data Preparation

The plan you develop from the exploration stage is executed here. Features may be dropped to keep the model simple. Continuous features are normalized. Categorical features are one-hot encoded. Balancing out classes, dropping columns, filling in missing values and also done at this stage. Once your data is cleaned and prepped, it's time to develop the model.

Modeling

Going into the phase, you may have determined the best model and simply need to refine it, or you may run a variety of models to determine which gives the best results for your dataset. The dataset needs to be split into testing and training sets at this stage.

Evaluation

Validation requires determining which metrics are best for the model you have chosen. A linear regression model looks to R-squared and p-values. Binary classification will be measured by accuracy and F1 scores. Once you've identified your metrics, you can test the model. Hypertuning parameters may also be done here.

Deployment

The final phase is deployment. This is where the hard work pays off and the model is used for its intended purpose. Using the model in the field is bound to generate a new set of questions, which will start the CRISP-DM process all over again.

