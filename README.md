# Machine Learning Regression Projects Collection  
**Beginner → Intermediate Level Hands-on Notebooks**  
*Linear Regression applied to real-world tabular datasets*

Last updated: March 2025  
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

### Complete Notebook Cells

```python
# ─── Cell 1 ─── Imports
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

sns.set_style("whitegrid")
%matplotlib inline

# ─── Cell 2 ─── Load data
df = pd.read_csv("student_performance_dataset.csv")
df.head(3)

# ─── Cell 3 ─── Target & features
target = 'Average_Score'
features = [
    'Gender', 'Age', 'Study_Hours_Per_Day', 'Attendance_Rate(%)',
    'Previous_Score', 'Tutoring_Support', 'Parent_Education',
    'Extracurricular', 'Sleep_Hours'
]
X = df[features].copy()
y = df[target]

# ─── Cell 4 ─── Column types
cat_cols = ['Gender','Tutoring_Support','Parent_Education','Extracurricular']
num_cols = ['Age','Study_Hours_Per_Day','Attendance_Rate(%)','Previous_Score','Sleep_Hours']

# ─── Cell 5 ─── Pipeline
preprocessor = ColumnTransformer([
    ('num', StandardScaler(), num_cols),
    ('cat', OneHotEncoder(drop='first'), cat_cols)
])

model = Pipeline([
    ('prep', preprocessor),
    ('reg', LinearRegression())
])

# ─── Cell 6 ─── Split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)

# ─── Cell 7 ─── Train
model.fit(X_train, y_train)

# ─── Cell 8 ─── Evaluate
y_pred = model.predict(X_test)
print(f"MAE:  {mean_absolute_error(y_test, y_pred):.2f}")
print(f"RMSE: {np.sqrt(mean_squared_error(y_test, y_pred)):.2f}")
print(f"R²:   {r2_score(y_test, y_pred):.3f}")

# ─── Cell 9 ─── Coefficients (run after training)
feature_names = num_cols + list(
    model.named_steps['prep'].named_transformers_['cat']
         .get_feature_names_out(cat_cols)
)
coefs = pd.Series(model.named_steps['reg'].coef_, index=feature_names).sort_values(ascending=False)
coefs.plot.barh(figsize=(9,7)); plt.title("Feature Coefficients"); plt.show()

# ─── Cell 10 ─── Example prediction
new_student = pd.DataFrame({
    'Gender':['Male'], 'Age':[16], 'Study_Hours_Per_Day':[6.5],
    'Attendance_Rate(%)':[88], 'Previous_Score':[82],
    'Tutoring_Support':['Yes'], 'Parent_Education':['Bachelor'],
    'Extracurricular':['Yes'], 'Sleep_Hours':[7.5]
})
print("Predicted average score:", round(model.predict(new_student)[0], 1))
