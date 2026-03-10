# Machine Learning Regression Projects Collection  
**Beginner → Intermediate Level Hands-on Notebooks**  
*Linear Regression applied to real-world tabular datasets*

Last updated: March 2026  
Author: Mir Shahadut  
Environment: Python 3.9+ / Jupyter Notebook / Google Colab compatible

---

## 📊 Overview of the Four Projects

| # | Dataset                          | Target Variable                  | Main Task                              | Key Features / Difficulty |
|---|----------------------------------|----------------------------------|----------------------------------------|----------------------------|
| 1 | Student Performance              | Average_Score / Math_Score       | Predict student academic performance   | ★★☆☆☆                     |
| 2 | House Prices                     | price                            | Classic house price regression         | ★★☆☆☆                     |
| 3 | Car Price Prediction             | Price(USD)                       | Used car price estimation              | ★★★☆☆                     |
| 4 | Employee Total Compensation      | Total_Compensation(USD)          | Salary & bonus prediction              | ★★★★☆                     |

All projects follow the same high-quality structure:

1. Imports & setup  
2. Data loading & quick EDA  
3. Feature selection & target definition  
4. Preprocessing pipeline (scaling + encoding)  
5. Train-test split  
6. Model training  
7. Evaluation (MAE / RMSE / R²)  
8. Coefficients interpretation  
9. Actual vs Predicted visualization  
10. Example prediction on new data

---

## 🎯 Project 1 – Student Performance Prediction

**Goal**: Predict `Average_Score` (or individual subject scores)  
**Dataset**: `student_performance_dataset.csv`

### Most important features (expected)

| Feature                  | Expected direction | Strength   |
|--------------------------|--------------------|------------|
| Previous_Score           | +                  | ★★★★★     |
| Study_Hours_Per_Day      | +                  | ★★★★☆     |
| Attendance_Rate(%)       | +                  | ★★★★☆     |
| Tutoring_Support_Yes     | +                  | ★★★☆☆     |
| Sleep_Hours              | + (up to ~8h)      | ★★☆☆☆     |


## 🎯 Project 2- House Price Prediction with Linear Regression  
**Classic Regression Project – Beginner to Intermediate**

![House Price Concept Banner](https://images.unsplash.com/photo-1580587771525-78b9e3f9dd10?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80)  
*Modern house valuation using machine learning*

**Last updated:** March 2026  
**Author:** Mir Shahadut  
**Environment:** Python 3.9+ / Jupyter Notebook / Google Colab

---

## 🎯 Project Objective

Build a **linear regression model** to predict house sale **price (USD)** based on basic property features:

- `size_sqft`  
- `bedrooms`  
- `age` (years since built)  
- `distance_city_km`

**Dataset:** `house_price_dataset.csv`

---

## 📊 Expected Feature Importance (Intuitive)

| Feature              | Expected Relationship with Price | Strength      | Reasoning                                      |
|----------------------|----------------------------------|---------------|------------------------------------------------|
| size_sqft            | **Strong positive**              | ★★★★★        | Larger houses usually cost significantly more |
| distance_city_km     | **Strong negative**              | ★★★★☆        | Farther from city center → lower value         |
| bedrooms             | **Positive** (with diminishing returns) | ★★★☆☆   | More bedrooms help, but not linearly forever   |
| age                  | **Negative**                     | ★★★☆☆        | Older houses often worth less (maintenance)    |

---

## 🛠️ Complete Jupyter Notebook Workflow

