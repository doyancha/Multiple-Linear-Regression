# Machine Learning Regression Projects Collection  
**Beginner → Intermediate Level Hands-on Notebooks**  
*Linear Regression applied to real-world tabular datasets*

Last updated: March 2026  
Author: Mir Shahadut  
Environment: Python 3.9+ / Jupyter Notebook / Google Colab compatible

---

# Regression Projects Collection  
**Student Performance · House Prices · Used Cars · Employee Compensation**

──────────────────────────────────────────────────────────────

## Overview – Four Linear Regression Learning Projects

| # | Project                          | Target                           | Main Theme                            | Difficulty | Key Insight                              |
|---|----------------------------------|----------------------------------|---------------------------------------|------------|------------------------------------------|
| 1 | Student Performance              | `Average_Score`                  | Academic success factors              | ★★☆☆☆      | Previous score dominates                 |
| 2 | House Prices                     | `price`                          | Classic real-estate valuation         | ★★☆☆☆      | Size matters most                        |
| 3 | Used Car Prices                  | `Price(USD)`                     | Automotive market pricing             | ★★★☆☆      | Year & mileage very strong               |
| 4 | Employee Total Compensation      | `Total_Compensation(USD)`        | Salary + bonus modeling               | ★★★★☆      | Base salary explains most variance       |

All projects use the same high-level workflow:

1. Imports & setup  
2. Data loading & quick look  
3. Feature + target selection  
4. Preprocessing (scaling + encoding)  
5. Train/test split  
6. Model training & evaluation  
7. Coefficients interpretation  
8. Actual vs Predicted plot  
9. Example prediction

──────────────────────────────────────────────────────────────

## Project 1 – Student Performance Prediction

**Goal**  
Predict student's `Average_Score` (or individual subject scores) based on study habits, background and support factors.

**Dataset**  
`student_performance_dataset.csv`

**Columns (most important)**

| Column                   | Type      | Meaning / Range                              |
|--------------------------|-----------|----------------------------------------------|
| Average_Score            | float     | Target (≈ average of Math/Reading/Writing)   |
| Previous_Score           | int       | Previous exam score (most predictive)        |
| Study_Hours_Per_Day      | float     | 0.5 – 10.0                                   |
| Attendance_Rate(%)       | int       | 50–99 %                                      |
| Tutoring_Support         | category  | Yes / No                                     |
| Sleep_Hours              | float     | 4–10 h                                       |
| Parent_Education         | category  | High School / Bachelor / Master / PhD       |
| Extracurricular          | category  | Yes / No                                     |

**Project Type**  
Supervised regression – **Beginner–Intermediate**

**Objectives**  
- Understand impact of study time, attendance, prior performance  
- See value of categorical encoding + standardization  
- Compare feature importance via coefficients

**Expected Feature Importance (Intuitive)**

| Rank | Feature                  | Expected direction | Strength |
|------|--------------------------|--------------------|----------|
| 1    | Previous_Score           | +                  | ★★★★★    |
| 2    | Study_Hours_Per_Day      | +                  | ★★★★☆    |
| 3    | Attendance_Rate(%)       | +                  | ★★★★☆    |
| 4    | Tutoring_Support_Yes     | +                  | ★★★☆☆    |
| 5    | Sleep_Hours              | + (up to ~8)       | ★★☆☆☆    |

