# California House Price Prediction

Predicting median house values across California districts using machine learning.
A **regression** project demonstrating the full ML workflow — from data exploration to
model comparison and evaluation.

---

## Overview

- **Problem:** Predict the median house value of a California district from
  demographic and housing features (a continuous-value regression task).
- **Data:** ~20,640 California districts (scikit-learn's California Housing dataset).
- **Best result:** R² ≈ 0.80 with a Random Forest Regressor
  (up from ≈ 0.58 for a Linear Regression baseline).

---

## The Data

Each row is a California district. The features describe the district; the target is
its median house value (in units of $100,000s).

| Feature | Meaning |
|---|---|
| `MedInc` | Median income of residents |
| `HouseAge` | Median house age in the district |
| `AveRooms` | Average number of rooms per household |
| `AveBedrms` | Average number of bedrooms per household |
| `Population` | District population |
| `AveOccup` | Average household occupancy |
| `Latitude` / `Longitude` | Location |
| **`MedHouseValue`** | **Target — median house value to predict** |

---

## What I Did

1. **Inspection** — checked shape, data types, ranges, and missing values before
   modeling. (The dataset is clean, but verifying is the discipline.)

2. **Exploratory Data Analysis (EDA)** — investigated which features drive price.
   Median income showed a strong positive correlation (~0.69) with house value,
   confirmed visually with a scatter plot.

3. **Train/test split** — held back 20% of districts as an untouched test set, so all
   evaluation reflects performance on data the model never learned from.

4. **Modeling & comparison** — trained a **Linear Regression** baseline, then compared
   it against a **Random Forest Regressor**. The Random Forest captured non-linear
   patterns a straight-line model can't, substantially improving accuracy.

5. **Evaluation** — measured performance with regression-appropriate metrics rather
   than classification accuracy.

---

## Results

| Model | R² | MAE | RMSE |
|---|---|---|---|
| Linear Regression | ~0.58 | ~0.53 | ~0.75 |
| Random Forest | ~0.80 | ~0.33 | ~0.51 |

*(MAE and RMSE are in units of $100,000s — e.g. an MAE of 0.33 ≈ being off by ~$33,000 on average.)*

**Why these metrics:**
- **MAE (Mean Absolute Error)** — average size of prediction errors, in real dollars.
- **RMSE (Root Mean Squared Error)** — like MAE but penalizes large misses more heavily;
  the gap between RMSE and MAE flags whether big errors are present.
- **R² (R-squared)** — fraction of price variation the model explains
  (0 = no better than guessing the average, 1 = perfect).

---

## Key Takeaways

- The Random Forest beat Linear Regression because house prices depend on **non-linear**
  relationships that a single straight line can't capture.
- **Income** is the single strongest predictor of house value.
- The right evaluation metric depends on the problem type — accuracy is meaningless for
  predicting a continuous value, so MAE, RMSE, and R² were used instead.

---

## Tools

Python · Pandas · NumPy · scikit-learn · seaborn · matplotlib

---

## How to Run

1. Open the notebook in [Google Colab](https://colab.research.google.com/) or Jupyter.
2. Run the cells top to bottom — the dataset loads automatically via scikit-learn
   (no download needed).

---

## What I'd Do Next

- Tune the Random Forest's settings (e.g. number and depth of trees) to push R² higher.
- Use cross-validation for a more robust performance estimate than a single split.
- Engineer new features (e.g. rooms-per-person) to capture more signal.

---

*Built by [Your Name] as a hands-on machine learning project.*
*[GitHub link / contact]*
