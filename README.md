# 🎓 Jamboree Linear Regression  
**Predicting Graduate Admissions using Linear & Regularized Regression**  

[![Python](https://img.shields.io/badge/Python-3.10-blue)]()  
[![Notebook](https://img.shields.io/badge/Notebook-Jupyter-orange)]()  
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()  

---

## 📌 Project Overview  
This project explores a dataset of **500 student admission profiles** (GRE, TOEFL, CGPA, SOP, LOR, University Rating, Research) to predict the **Chance of Admit**.  

The workflow covers:  
- **Exploratory Data Analysis (EDA)** — correlations, distributions, and feature insights.  
- **Linear Regression** — baseline predictive model.  
- **Regularization** — Ridge (L2), Lasso (L1), and Elastic Net.  
- **Regression Assumptions Testing** — multicollinearity, linearity, residual normality, and homoscedasticity.  

Key finding: **CGPA is the strongest predictor of admission chances**, while SOP and University Rating contribute the least.  

---

## 🗂 Dataset  
- **Size**: 500 rows × 9 columns  
- **Features**: GRE, TOEFL, University Rating, SOP, LOR, CGPA, Research  
- **Target**: Chance of Admit (float, 0–1)  

**Preprocessing**:  
- Dropped irrelevant columns (`Serial No.`).  
- Renamed inconsistent column names (`LOR ` → `LOR`, `Chance of Admit ` → `Chance of admit`).  
- Standardized features with `StandardScaler`.  

---

## ⚙️ Methodology  

### 1. Exploratory Data Analysis  
- Heatmaps, histograms, scatter plots, violin plots.  
- Observed strong positive correlation among GRE, TOEFL, and CGPA.  
- Distribution analysis showed GRE/TOEFL ~ Gaussian.  

### 2. Model Building  
- **Linear Regression** → baseline model (R² ≈ 0.82).  
- **Ridge Regression** → reduced coefficient variance.  
- **Lasso Regression** → shrunk less relevant coefficients.  
- **Elastic Net** → balanced Ridge + Lasso.  

### 3. Model Evaluation  
Metrics: **MAE, RMSE, R², Adjusted R²**  

Example (Linear Regression):  
- Training R²: 0.82  
- Test R²: 0.82  
- MAE: ~0.043  
- RMSE: ~0.061  

### 4. Assumptions Tested  
- ✅ Multicollinearity → High VIF (>5) for GRE, TOEFL, CGPA (expected correlation).  
- ✅ Residual mean ~ 0 → unbiased.  
- ✅ Residuals ~ normal distribution (QQ plot, KDE).  
- ✅ Homoscedasticity present.  
- ✅ Linearity holds (residual plots show no patterns).  

---

## 📊 Key Results  

- **CGPA** → most significant predictor.  
- **SOP & University Rating** → least impactful features.  
- Regularization models performed comparably to simple Linear Regression.  
- Models consistently explained ~**82% variance in admission chances**.  

---

## 🔧 Dependencies  

```txt
python>=3.9
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
scipy
jupyterlab
