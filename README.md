# Calories Burned Prediction Using Machine Learning

## Project Overview
This project aims to predict the number of calories burned during physical exercise based on personal attributes and activity features such as age, weight, duration, heart rate, and body temperature.  
It demonstrates a complete **ML pipeline** including EDA, preprocessing, modeling, evaluation, feature importance, hyperparameter tuning, and inference.

---

## Dataset
The dataset contains two main CSV files:

1. **exercise.csv**  
   - Features: `User_ID`, `Gender`, `Age`, `Height`, `Weight`, `Duration`, `Heart_Rate`, `Body_Temp`
   
2. **calories.csv**  
   - Target: `Calories` burned  
   
The datasets were merged on `User_ID` to form the final dataset for modeling.

**Source:** [Kaggle - fmendes DAT263x Demos](https://www.kaggle.com/datasets/fmendes/fmendesdat263xdemos)

---

## Project Steps

### 1. Data Understanding & EDA
- Loaded and explored the dataset.
- Performed **univariate analysis** (distributions of numerical features and target variable).
- Conducted **bivariate analysis** to explore feature-target relationships.
- Created a **correlation matrix** to identify important predictors.

### 2. Data Preprocessing & Feature Engineering
- Categorical variable `Gender` encoded (male=1, female=0).
- Engineered new features:
  - **BMI** (Body Mass Index)
  - **Duration_Weight_Ratio**
- Scaled numerical features using `StandardScaler`.
- Split the dataset into **train (80%)** and **test (20%)** sets.

### 3. Baseline Regression Model
- Built **Linear Regression** model as baseline.
- Evaluated using **R², MAE, RMSE**.
- Conducted residual analysis to check linearity and variance.
- Examined feature coefficients for insights.

### 4. Advanced Models & Model Improvement
- Trained **Random Forest Regressor** and **Gradient Boosting Regressor**.
- Tuned Random Forest using **GridSearchCV**.
- Selected **Tuned Random Forest** as final model.
- Calculated **feature importance**:
  - Most important: `Duration`, `Heart_Rate`, `BMI`

### 5. Inference & Prediction
- Built a pipeline for predicting calories for new users.
- Ensured preprocessing steps are applied to new input (encoding, feature engineering, scaling).
- Example:
Sample Input:
  Gender: Male
  Age: 30
  Height: 175
  Weight: 70
  Duration: 45 min
  Heart Rate: 120 bpm
  Body Temp: 37.0 °C

Predicted Calories Burned: 226.81 kcal

- Explained contribution of features to the prediction.

---

## Key Insights
- Exercise **Duration** and **Heart Rate** are the most influential factors affecting calories burned.
- Feature engineering like **BMI** and ratios improved model performance.
- Random Forest outperforms baseline Linear Regression with higher R² and lower error metrics.
- Pipeline is ready for **new user prediction** and can be used in a real-world fitness application.

---

## Project Pipeline Overview

```text
Data Loading → EDA → Preprocessing → Feature Engineering → Train/Test Split
→ Baseline Regression → Advanced Models → Hyperparameter Tuning → Final Model
→ Sample Prediction & Inference → Insights

