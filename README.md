# Machine Learning Regression Projects Collection
![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Jupyter](https://img.shields.io/badge/jupyter-notebook-orange)
![Colab](https://img.shields.io/badge/Google%20Colab-compatible-red)
![License](https://img.shields.io/badge/license-MIT-green)

**Beginner → Intermediate Level Hands‑on Notebooks**  
*Linear Regression applied to real‑world tabular datasets with full end‑to‑end pipelines and interpretability guidance.*

Last updated: March 2026  
Author: Mir Shahadut  
Environment: Python 3.9+ / Jupyter Notebook / Google Colab compatible

---

## 🔍 Introduction
This repository bundles four self‑contained machine learning projects that showcase how to build, evaluate, and interpret linear regression models on real‑world datasets. The materials are geared toward students, aspiring data scientists, and analysts who want a hands‑on, expert‑level walkthrough of regression workflows in Python.

Each notebook is fully annotated, reproducible, and designed to run either locally or in Google Colab. While the core focus is on ordinary least squares, the discussions frequently point out when and why you might transition to regularized or tree‑based models.

---

## ✅ Highlights
- **Four distinct domains:** education, real estate, automotive, and HR analytics.  
- **Common pipeline:** data loading → preprocessing → modelling → diagnostics → interpretation.  
- **Clean, modular code:** easily extendable for experimentation.  
- **Interpretability emphasis:** coefficient tables, standardized features, and visualizations.  
- **Learning path:** from basic assumptions to advanced tweaks (log transforms, polynomial features, regularization).

---

## 🗂 Project overview
| # | Project                          | Target                           | Theme                                 | Difficulty | Key Insight                              |
|---|----------------------------------|----------------------------------|---------------------------------------|------------|------------------------------------------|
| 1 | Student Performance              | `Average_Score`                  | Academic success factors              | ★★☆☆☆      | Previous score dominates                 |
| 2 | House Prices                     | `price`                          | Classic real‑estate valuation         | ★★☆☆☆      | Size matters most                        |
| 3 | Used Car Prices                  | `Price(USD)`                     | Automotive market pricing             | ★★★☆☆      | Year & mileage very strong               |
| 4 | Employee Total Compensation      | `Total_Compensation(USD)`        | Salary + bonus modelling               | ★★★★☆      | Base salary explains most variance       |

All projects share the same high‑level workflow:

1. Imports & setup  
2. Data loading & quick look  
3. Feature + target selection  
4. Preprocessing (scaling + encoding)  
5. Train/test split  
6. Model training & evaluation  
7. Coefficients interpretation  
8. Actual vs Predicted plot  
9. Example prediction

---

## 📦 Getting started
### Prerequisites
- Python 3.9 or newer  
- `pip` (or `conda`)  
- Jupyter Notebook / JupyterLab or Google Colab  

Required Python packages (see `requirements.txt` for pin‑versions):
```
pandas numpy scikit-learn matplotlib seaborn
```  
(Optionally: `xgboost`, `lightgbm` for extension exercises.)

### Installation
```bash
git clone https://github.com/<your‑username>/multiple-linear-regression.git
cd multiple-linear-regression
python -m venv .venv            # or use conda
.venv\Scripts\activate        # Windows
pip install -r requirements.txt
jupyter notebook               # or jupyter lab
```

Or open any notebook directly in Google Colab via the badge at the top of each file.

### Project structure
```
CAR PRICE PREDICTION.ipynb
data/car_price_prediction_dataset.csv
EMPLOYEE SALARY PREDICTION.ipynb
…
README.md
requirements.txt
```  
Every notebook reads its corresponding CSV from the root directory. Feel free to reorganize as you prefer.

### Running the notebooks
t1. Launch Jupyter and click a notebook name.  
2. Execute cells in order (Shift+Enter).  
3. Inspect plots, coefficients, and comments as you go.  

Each notebook includes a `# %%`‑style Python script at the bottom that can be exported for production use.

---

## 📊 Dataset summaries
- **student_performance_dataset.csv**: test scores with study habits, attendance, parental education, etc.  
- **house_price_dataset.csv**: housing features such as square footage, bedrooms, distance to city centre, age.  
- **car_price_prediction_dataset.csv**: used‑car listings with mileage, year, brand, condition, etc.  
- **employee_salary_dataset.csv**: anonymised compensation records including base salary, job level, experience, department.

All CSVs are synthetic yet realistic; they are distributed under the MIT license. You can augment or replace them with your own data.

---

## 🧠 Advanced tips & extensions
- Apply **log‑transform** to skewed targets (price, compensation).  
- Add **polynomial** or **interaction** features for non‑linearity.  
- Swap `LinearRegression` for `Ridge`/`Lasso` and compare coefficients.  
- Transition to **tree‑based** models (RandomForest/XGBoost/LightGBM) for a 15‑30 % boost in R².  
- Diagnose problems with **residual plots**, **QQ plots**, and **heteroscedasticity tests**.  
- Use cross‑validation and grid search for hyperparameter tuning.

---

## 🚧 Contributing
Improvements, bug reports, and feature requests are welcome!  
1. Fork this repository.  
2. Create a new branch (`git checkout -b feature/foo`).  
3. Commit your changes with clear messages.  
4. Open a pull request against `main`.  

Please follow the existing style and add comments where necessary. If you add a new dataset or notebook, update this README accordingly.

---

## 📜 License
This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact
Mir Shahadut  
Email: mir.shahadut@example.com  
GitHub: [@mirshahadut](https://github.com/mirshahadut)

---

## 🙏 Acknowledgements
Datasets are inspired by publicly available educational, housing, automotive and HR compensation data.  
Thanks to the scikit‑learn and pandas communities for excellent documentation and tooling.

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

## Final Recommendations for All Four Projects

Here are practical next steps to level up your regression models across **Student Performance**, **House Prices**, **Used Cars**, and **Employee Compensation** projects:

- Try log-target when prices/salaries are right-skewed  
- Experiment with polynomial features (especially experience, size, mileage)  
- Compare Ridge / Lasso vs plain LinearRegression  
- Move to tree-based models (Random Forest → XGBoost → LightGBM) — usually +15–30% R²  
- Always look at residual plots to diagnose problems

Good luck with your regression learning journey!  

Mir Shahadut  
March 2026 – Dhaka
| 5    | Performance_Rating             | +                               | ★★★☆☆      |

──────────────────────────────────────────────────────────────
