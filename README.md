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


## Project 2 – House Price Prediction

**Goal**  
Predict house sale price using basic structural and location features.

**Dataset**  
`house_price_dataset.csv`

**Project Type**  
Classic regression benchmark – Beginner–Intermediate

**Objectives**

- Understand how structural features (especially living area size) and location (distance to city center) drive house prices  
- Observe the strong linear relationship between square footage and price  
- See the negative impact of distance and age — and how standardization helps interpret coefficients meaningfully  
- Compare relative importance of features through regression coefficients  
- Recognize when linear assumptions hold well (or start to break) in real-estate data

**Expected Feature Importance (Intuitive)**

| Feature            | Expected direction       | Strength   |
|--------------------|--------------------------|------------|
| size_sqft          | Strong positive          | ★★★★★      |
| distance_city_km   | Strong negative          | ★★★★☆      |
| bedrooms           | Positive (diminishing)   | ★★★☆☆      |
| age                | Negative                 | ★★★☆☆      |

──────────────────────────────────────────────────────────────

## Project 3 – Used Car Price Prediction

**Goal**  
Estimate used car `Price(USD)` from make, model year, mileage, etc.

**Dataset**  
`car_price_prediction_dataset.csv`

**Project Type**  
Tabular regression with categorical encoding – Intermediate

**Objectives**

- Understand the dominant effect of **year** and **mileage** on used car pricing  
- Learn how to handle multiple categorical variables (brand, fuel type, transmission, condition) through one-hot encoding  
- Observe how standardization changes coefficient interpretation for numerical features (mileage, engine size, age)  
- Compare feature importance via coefficients — especially to see which brands carry a premium  
- Recognize common real-world issues: non-linear depreciation, brand effects, and interaction between age and mileage

**Expected Feature Importance (Intuitive)**

| Rank | Feature              | Expected direction   | Strength   |
|------|----------------------|----------------------|------------|
| 1    | Year                 | +                    | ★★★★★      |
| 2    | Mileage(km)          | –                    | ★★★★★      |
| 3    | Brand (premium)      | +                    | ★★★★☆      |
| 4    | Accidents_Reported   | –                    | ★★★☆☆      |
| 5    | Engine_Size(L)       | +                    | ★★★☆☆      |

──────────────────────────────────────────────────────────────

## Project 4 – Employee Total Compensation Prediction

**Goal**  
Predict `Total_Compensation(USD)` = base salary + bonus

**Dataset**  
`employee_salary_dataset.csv`

**Project Type**  
Business / HR analytics regression – Intermediate–Advanced

*Objectives**

- Understand how strongly **base salary** dominates total compensation prediction  
- See the added value of job level, experience, department, and performance rating beyond base pay  
- Learn the effect of including vs excluding base salary (very different difficulty & R²)  
- Observe how categorical encoding reveals compensation differences across departments, locations, education levels, etc.  
- Compare feature importance via coefficients — especially to quantify the premium for seniority, education, and remote work  
- Recognize when linear regression works very well (with base salary) vs when tree-based models become clearly superior (without it)

**Expected Feature Importance (Intuitive)**

| Rank | Feature                        | Expected direction              | Strength   |
|------|--------------------------------|---------------------------------|------------|
| 1    | Base_Salary(USD)               | +                               | ★★★★★      |
| 2    | Job_Level (Director/Sr)        | +                               | ★★★★☆      |
| 3    | Experience_Years               | +                               | ★★★★☆      |
| 4    | Department (Eng/Finance)       | + vs HR/Marketing               | ★★★☆☆      |
| 5    | Performance_Rating             | +                               | ★★★☆☆      |

──────────────────────────────────────────────────────────────
