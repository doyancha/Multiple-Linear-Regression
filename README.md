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


