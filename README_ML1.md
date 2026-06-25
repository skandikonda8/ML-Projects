# Titanic Survival Prediction

Predicting passenger survival on the Titanic using machine learning.
A binary classification project demonstrating the full ML workflow.

## Overview
- **Problem:** Predict whether a passenger survived from demographic and ticket data.
- **Data:** 891 passengers (Seaborn's Titanic dataset).
- **Result:** ~82% accuracy with a Random Forest classifier.

## What I did
1. **Data cleaning** — handled missing ages (median) and ports (mode); removed a leakage column.
2. **EDA** — found women survived at ~74% vs ~19% for men; 1st class ~63% vs ~24% for 3rd.
3. **Modeling** — compared Logistic Regression, Decision Tree, and Random Forest.
4. **Interpretation** — feature importance confirmed sex, fare, and age mattered most.

## Tools
Python, Pandas, scikit-learn, seaborn, matplotlib.

## Key takeaway
Demonstrates an end-to-end ML pipeline: cleaning, exploration, model comparison, and evaluation.

