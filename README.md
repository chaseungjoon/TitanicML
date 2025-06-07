# Titanic Survivor

---

---

https://www.kaggle.com/competitions/titanic/overview

# Overview

Create a machine learning model that predicts the survivability of passengers. The passengers have features that can determine their survival.

---

# Data

- Training set (train.csv)
- Test set (test.csv)

## Data Dictionary

| Variable | Definition | Key |
| --- | --- | --- |
| survival | Survival | 0=No, 1=Yes |
| pclass | Ticket Class | 1=1st, 2=2nd, 3=3rd |
| sex | Sex |  |
| age | Age in years |  |
| sibsp | # of siblings / spouses aboard the Titanic |  |
| parch | # of parents / children aboard the Titanic |  |
| ticket | Ticket number |  |
| fare | Passenger fare |  |
| cabin | Cabin number |  |
| embarked | Port of Embarkation | C=cherbourg, Q=Queenstown, S=southampton |
- pclass : A proxy for socio-economical status (SES)
    - 1st = Upper
    - 2nd = Middle
    - 3rd = Lower
- age : Age is fractional if less than 1. If the age is estimated, is it in the form of xx.5
- sibsp : The dataset defines family relations in this way
    - Sibling = brother, sister, stepbrother, stepsister
    - Spouse = husband, wife (mistresses and fiancés were ignored)

## Submission Type

CSV file containing 2 columns 

- PassengerId (sorted in any order)
- Survived (1 for survived, 0 for deceased)

---

# Model

- Base Model : Ridge
- Polynomial Features : Degree 2
- alpha (regularization strength) : tones down overfitting coefficients when increased

## Relevant Features

- pclass : lower pclass has higher chance or survival
- sex : female has higher chance of survival
- age : extreme values (high or low) have higher chance of survival
- fare : high fare has higher chance or survival
- cabin : non-Nan values have higher chance or suvival

---

# Results

- Ridge

| Alpha Value | Score |
| --- | --- |
| 1 | 0.76794 |
| 10 | 0.77511 |
| 50 | 0.77272 |
- Logistic Regression

| C Value | Score |
| --- | --- |
| 1 | 0.77033 |
| 0.1 | 0.75598 |
| 5 | 0.77272 |