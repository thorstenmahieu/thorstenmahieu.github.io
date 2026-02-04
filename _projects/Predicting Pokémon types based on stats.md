---
tags:
  - group-work
  - school-project
  - data-science
  - machine-learning
  - artificial-intelligence
  - programming
programming-language: Python
layout: project
start-date: 2024-03
title: "Predicting Pokémon types based on stats"
permalink: projects/pokémon-types-classification/
rating: 4/5
---

This group project involved designing a **machine learning pipeline** to predict Pokémon types based on their stats. The dataset, "Pokémon with Stats," included 721 Pokémon with features like HP, Attack, Defense, Special Attack, Special Defense, and Speed.

## Objectives

1. Predict Pokémon types (Type 1 and Type 2) using their stats.
2. Compare various machine learning models to determine the most accurate approach.
3. Preprocess data for effective model training and validation.

## Features and Functionality

1. **Dataset Preprocessing**:
   - Filled missing values for Type 2 with "None."
   - Applied one-hot encoding to categorical variables.
   - Scaled numerical features to ensure consistency.
2. **Machine Learning Models**:
   - Explored models including Random Forests, Decision Trees, Support Vector Machines (SVM), Logistic Regression, and K-Nearest Neighbors (KNN).
   - Performed hyperparameter tuning with GridSearchCV and RandomizedSearchCV.
3. **Validation and Metrics**:
   - Used train/test splits and k-fold cross-validation.
   - Evaluated models using accuracy, precision, recall, and F1-score.
The entire pipeline has been coded in a Jupyter Notebook
## Results

- For the [base dataset](/assets/main.html), Random Forests achieved the best accuracy (86%) for multilabel classification when predicting type combinations without considering order.
- With an expanded [dataset](/assets/larger%20dataset.html) including additional features like height, weight, and abilities, Random Forests achieved 96% accuracy under the same conditions.
- Stratification was applied to address imbalances in rare type combinations.

## Conclusion

The project demonstrated that **Random Forests** provided the most accurate results for predicting Pokémon types. Future steps could include exploring deep learning models, addressing missing data in the expanded dataset, and refining feature selection for improved performance.

---  
*Technologies used*: scikit-learn
*Project team*: Thorsten Mahieu, Cédric Chau  
*Time range*: March 2024 - May 2024  