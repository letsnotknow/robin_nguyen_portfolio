# Telecom Marketing Campaign Optimisation

End-to-End EDA and Predictive Modelling

## Overview

This project analyses a telecommunications marketing campaign to identify which customers are most likely to subscribe to a new plan and how outreach strategy affects conversion.

The work moves from statistical exploratory analysis to predictive modelling, with a focus on business interpretability, leakage prevention, and recall optimisation.

---

## Dataset

* 41,180 customers
* 20 features
* Subscription rate: 11.26% (high class imbalance)

Feature groups include:

* Demographics (age, job, education)
* Financial indicators (default, loans)
* Campaign details (contact type, number of attempts)
* Past campaign history (poutcome, pdays)
* Macroeconomic signals (euribor3m, employment indicators)

---

# Part 1: Exploratory Data Analysis

Key steps:

* Removed duplicates and handled unknown labels
* 80/20 stratified train-test split
* Removed leakage variable (call duration)
* Log-transformed skewed features
* Tested interactions and multicollinearity

### Main Insights

**Contact fatigue**
More contact attempts reduce subscription probability.

**Channel effect**
Cellular contact significantly outperforms telephone.

**Age × Job interaction**
Customer responsiveness depends jointly on demographic and occupational factors.

**Past campaign outcome**
Previous success (poutcome) is one of the strongest predictors.

**Macroeconomic influence**
Lower euribor3m rates are associated with higher conversion.
Due to multicollinearity, euribor3m was retained as the primary macro signal.

---

# Part 2: Predictive Modelling

## Modelling Approach

* Pre-contact features only
* Class weighting to address imbalance
* Recall prioritised over accuracy
* Interaction terms included selectively
* Multicollinearity reduced via feature selection

## Models Implemented

* Logistic Regression (interpretable baseline)
* Tree-based ensemble models

## Evaluation Metrics

* Recall (primary)
* PR-AUC
* ROC-AUC
* Confusion matrix

Tree-based models improved recall performance over logistic regression.

---

# Business Recommendations

1. Default to cellular contact.
2. Limit repeated outreach to prevent fatigue.
3. Prioritise customers with prior successful outcomes.
4. Use recall-optimised models for campaign targeting.

---

## Tech Stack

Python
Pandas
NumPy
Seaborn / Matplotlib
Statsmodels
Scikit-learn

---

## Project Demonstrates

* Statistical hypothesis testing
* Interaction modelling
* Multicollinearity handling
* Class imbalance strategy
* End-to-end analytics workflow