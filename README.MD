#  🛳️ Titanic - Machine Learning Project

This project is inspired by the competition [Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic) from Kaggle.

> The competition is simple: use machine learning to create a model that predicts which passengers survived the Titanic shipwreck.

## Project Overview

1. <a href="#step1"> Exploratory Data Analysis </a> <br>
2. <a href="#step2"> Feature Engineering </a> <br>
3. <a href="#step3"> Data Preprocessing </a> <br>
4. <a href="#step4"> Model Building </a> <br>
5. <a href="#step5"> Model Tuning </a> <br>
6. <a href="#step6"> Model Evaluation </a> <br>
7. <a href="#step7"> Model Results </a> <br>


<h2 id="step1">
  1. Exploratory Data Analysis
</h2>

In this step, an overview of the dataset was performed, followed by a column-by-column analysis. Numeric variables were examined for their distribution and correlation with survival, while categorical variables were analyzed for passenger count per feature and survival rates grouped by each feature.

<h2 id="step2">
  2. Feature Engineering
</h2>

Certain variables required modification to improve their fit for the model. Feature engineering was performed on the following columns:

- Age, to create Age Bands;
- Name, to extract Titles;
- SibSp and Parch, to determine whether family members were present on board;
- Cabin, to determine whether the cabin was shared with other passengers.

<h2 id="step3">
  3. Data Preprocessing
</h2>

This step involved the following actions for preprocessing the data before model building:

- Select only the necessary columns for model building;
- Split data into X and Y;
- One-Hot-Encode nominal columns;
- Train-test-split the data set;
- Scale the X data set.

<h2 id="step4">
  4. Model Building
</h2>

Initially, 6 different classification algorithms were tested to establish a baseline validation performance using 5-fold cross-validation:

- Logistic Regression;
- K — Nearest Neighbors;
- Support Vector Machine;
- Naive Bayes;
- Decision Tree Classifier;
- Random Forest.

The models were constructed using default parameters to enable comparison of improvement through model tuning at a later stage.

The baseline validation performance can be seen below:

| |Baseline Model Accuracy|
|----|----|
|Logistic Regression|78.82%|
|K-Nearest Neighbors|81.54%|
|Support Vector Machine|81.06%|
|Naive Bayes|70.27%|
|Decision Tree|78.18%|
|Random Forest|78.81%|

<h2 id="step5">
  5. Model Tuning
</h2>

Model tuning with GridSearchCV for finding the optimal hyperparameters to increase the models performance.

After model tuning, all models demonstrated improved results, except for the SVM and Random Forest models, which retained their original levels of accuracy:

| |Baseline Model Accuracy|Model Tuned Accuracy|
|----|----|----|
|Logistic Regression|78.82%|79.78%|
|K-Nearest Neighbors|81.54%|81.71%|
|Support Vector Machine|81.06%|81.06%|
|Naive Bayes|70.27%|78.82%|
|Decision Tree|78.18%|81.22%|
|Random Forest|78.81%|78.81%|

<h2 id="step6">
  6. Model Evaluation
</h2>

Since a better validation performance does not necessarily imply a better performance in predicting the test data set, in this step a final model evaluation was performed with the test data set, using the tuned models. 

**Random Forest** model accuracy score was the highest among models for the testing set.

| |Model Accuracy for the testing set|
|----|----|
|Logistic Regression|80.6%|
|K-Nearest Neighbors|82.09%|
|Support Vector Machine|83.21%|
|Naive Bayes|79.85%|
|Decision Tree|80.22%|
|Random Forest|83.58%|

<h2 id="step7">
  7. Model Results
</h2>

Below are a few highlights of the model results:

<img src="https://i.ibb.co/74ZG18d/download.png" width=30% height=70%>
<img src="https://i.ibb.co/SrkZgDC/download-1.png" width=30% height=70%>

<p align="center">
<img src="https://i.ibb.co/7SWZXFf/download-2.png" width=100% height=70%>

