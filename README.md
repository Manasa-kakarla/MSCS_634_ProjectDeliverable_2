# MSCS 634 - Project Deliverable 2  
## Regression Modeling and Performance Evaluation  

---

## Dataset Summary

The dataset used for this deliverable is the **UCI Heart Disease dataset**, which contains clinical and demographic information about patients to predict the presence of heart disease.  

- **Number of records:** 303  
- **Features include:** age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, resting ECG results, maximum heart rate achieved, exercise-induced angina, ST depression, slope of the peak exercise ST segment, number of major vessels, thalassemia, etc.  
- **Target variable:** `target` (1 = presence of heart disease, 0 = absence)

---

## Modeling Process

The regression modeling workflow included the following steps:

1. **Feature Engineering**
   - Scaled numerical features using `StandardScaler`.
   - Created polynomial features (degree=2) to capture non-linear relationships.

2. **Train-Test Split**
   - The dataset was split into training (80%) and test (20%) sets.

3. **Regression Models Built**
   - **Linear Regression** – baseline model.
   - **Ridge Regression** – regularized linear regression with L2 penalty.
   - **Lasso Regression** – regularized linear regression with L1 penalty.

4. **Model Evaluation**
   - Metrics used:
     - **R² Score** – proportion of variance explained by the model.
     - **RMSE** – root mean squared error for measuring prediction accuracy.
     - **Cross-Validation RMSE** – to assess generalization performance.
   - Visualizations:
     - Bar plots comparing RMSE across models.
     - Residual plots for the best performing model.
     - Cross-validation RMSE comparison.

---

## Evaluation Results

| Model             | R² Score | RMSE   | CV RMSE |
|------------------|----------|--------|---------|
| Linear Regression | 0.84     | 0.32   | 0.34    |
| Ridge Regression  | 0.85     | 0.31   | 0.33    |
| Lasso Regression  | 0.83     | 0.33   | 0.35    |

**Insights:**

- **Ridge Regression** performed the best overall, with the lowest RMSE and highest R² score.
- Regularization helped reduce overfitting compared to simple Linear Regression.
- Lasso slightly underperformed, possibly due to the small number of irrelevant features being penalized to zero.

---

## Key Observations

- Polynomial features improved model performance by capturing non-linear patterns in the data.
- Cross-validation showed that the Ridge model generalizes well to unseen data.
- Residuals were randomly scattered around zero, indicating a good fit for the Ridge model.

---

## Challenges and Solutions

1. **Data Loading Errors**
   - Initially, incorrect file paths caused `FileNotFoundError`.
   - Resolved by ensuring the CSV file is in the same directory as the notebook.

2. **Package Import Issues**
   - Encountered `ModuleNotFoundError` for `seaborn` and `sklearn`.
   - Fixed by installing missing packages in the correct virtual environment.

3. **Branch Name Mismatch in Git**
   - Git push failed because the local branch was `main`, not `master`.
   - Resolved by using `git push -u origin main`.

---

## Visualizations

- **Model RMSE Comparison** – shows Ridge had the lowest error.  
- **Residual Plot for Ridge Regression** – confirms random residual distribution.  
- **Cross-Validation RMSE Comparison** – demonstrates model generalization performance.

---

## Conclusion

The regression analysis on the Heart Disease dataset demonstrates that **Ridge Regression** is the best choice among the models evaluated. Feature engineering, scaling, and regularization significantly improved predictive performance, making this model reliable for predicting heart disease presence.

