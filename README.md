# 🌌 Galaxy Well-Being Index Prediction

## Author: Valerie Jerono  
**Program:** MSc Data Science and Analytics (Scholarship Exam, 2025)  
**Dataset:** `Train_data.csv` (3,097 rows × 81 columns)  

---

## 🔍 Objective

To identify key socio-economic and demographic indicators influencing the **Well-Being Index** across galaxies and build a **predictive model** to estimate future values with **high accuracy**.

---

## 📊 Dataset Overview

- **Observations:** 3,097 galaxy-year records
- **Features:** 80 input features + 1 target (`Well-Being Index`)
- **Time Span:** Up to 26 years across 181 galaxies
- **Target Variable:** Continuous → Regression problem

---

## 🧹 Workflow Summary

### 1. Data Understanding
- Inspected missing values, data types, and distributions.
- Identified features with extreme missingness (>70%).

### 2. Feature Selection
- Correlated all variables with `Well-Being Index`.
- Dropped:
  - **Negatively or weakly correlated** features.
  - **Mid-correlation features** with missing values.
- Kept **30 high-correlation features** for modeling.

### 3. Data Cleaning & Imputation
- Used **KNN Imputer** for missing values in key features.
- Created binary `*_missing_flag` indicators.
- Standardized and stripped column names.

---

## 🤖 Modeling

### Models Evaluated:
| Model                  | RMSE    | R²     |
|------------------------|---------|--------|
| Ridge Regression       | 0.0278  | 0.8454 |
| Linear Regression      | 0.0279  | 0.8450 |
| Random Forest Regressor| 0.0292  | 0.8299 |
| Decision Tree          | 0.0443  | 0.6076 |
| Dummy Regressor        | 0.0721  | -0.037 |

➡️ **Linear Regression** selected for deployment due to its simplicity, competitive RMSE, and strong generalizability.

---

## ✅ Output & Files

- **Predictions CSV**: `Valerie_Jerono_DSA.csv`
- **Final Model**: Linear Regression
- **Notebook**: Jupyter notebook with full workflow
- **Presentation**: 5-slide PDF summary

---

## 📌 Recommendations

1. Use **Linear Regression** for deployment.
2. Focus policy on education, income, and life expectancy.
3. Improve **data completeness** for key features.
4. **Retrain annually** to reflect evolving galactic trends.

---

## 📂 File Structure

```bash
├── Valerie_Jerono_DSA.ipynb       # Full notebook
├── Valerie_Jerono_DSA.csv         # Predictions for validation set
├── README.md                      # This file
├── slides_summary.pdf             # 5-slide presentation (summary)
├── data/
│   ├── Train_data.csv
│   ├── Validation.csv
│   └── imputed_train_data.csv
