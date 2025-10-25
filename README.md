# 🏥 ICU Predictions: Data-Driven Clinical Outcome Modeling

This project explores how patient vital signs, laboratory results, and severity scores can be used to predict **in-hospital mortality** and **ICU admissions** using machine learning models.  
The dataset simulates real ICU data from electronic health records (EHR), inspired by publicly available critical care datasets such as MIMIC-III.  
It focuses on early recognition of deterioration and data-driven decision support in clinical settings.

---

## 📊 About the Dataset

**Source:** Simulated ICU EHR data (inspired by MIMIC-III)  
**Files:**
- `X_train_2025.csv` — 3,600 patient records with 120 clinical, demographic, and treatment-related features  
- `In-hospital_death` — Binary target variable (0 = survived, 1 = died)

### Key Feature Groups
- **Demographics:** Age, Gender, Height, Weight  
- **Severity Scores:** SAPS-I, SOFA  
- **Vital Signs:** HR, RespRate, MAP, SaO₂, Temp (multiple time-points: first, last, lowest, highest, median)  
- **Lab Results:** Albumin, AST, ALT, Bilirubin, BUN, Creatinine, Glucose, etc.  
- **Ventilation Data:** MechVentStartTime, MechVentDuration, UrineOutputSum  
- **ICU Indicators:** CCU, CSRU, SICU — combined into a single `ICU_Admission` variable  

---

## ⚙️ Project Workflow

### 1. **Data Cleaning**
- Dropped all columns with more than **35% missing values**
- Imputed remaining missing values using **median imputation**
- Combined ICU columns (`CCU`, `CSRU`, `SICU`) into a unified `ICU_Admission` binary variable  

### 2. **Exploratory Data Analysis (EDA)**
- Summary statistics (`mean`, `std`, `skew`, `kurtosis`)
- Missing value visualization and NA thresholding
- Correlation analysis between clinical features and outcomes
- Feature distribution and outlier detection  

### 3. **Feature Engineering**
- Standardized numeric features using **StandardScaler**
- Removed low-variance and highly correlated features  
- Selected features based on correlation and clinical relevance  

### 4. **Modeling**
Current model: **Logistic Regression (baseline)**  
- Evaluated using accuracy, classification report, and ROC-AUC score  
- Feature importance interpreted via coefficient weights and odds ratios  

**Coming Soon 🚧**
- Random Forest & XGBoost comparisons  
- Hyperparameter tuning (GridSearchCV)  
- Cross-validation performance metrics  

### 5. **Evaluation**
- Accuracy, Precision, Recall, and F1-score  
- Confusion matrix and ROC curve visualizations  
- Correlation matrix of test set for feature dependency insights  

**Coming Soon 🚧**
- SHAP feature explainability  
- Calibration curves for clinical interpretability  

---

## 🧠 Results Summary

| Metric | Logistic Regression |
|--------|--------------------|
| Accuracy | *Coming Soon 🚧* |
| ROC-AUC | *Coming Soon 🚧* |
| Top Predictors | SOFA, SAPS-I, HR_highest, SaO₂_lowest, BUN_last |

---

## 🧩 Project Structure

icu-predictions/
│
├── data/
│ ├── X_train_2025.csv
│ └── (coming soon: cleaned_data.csv)
│
├── notebooks/
│ ├── 01_data_cleaning.ipynb
│ ├── 02_eda.ipynb
│ ├── 03_modeling.ipynb
│ └── (coming soon: 04_model_comparison.ipynb)
│
├── scripts/
│ ├── preprocess.py
│ ├── train_model.py
│ └── evaluate.py
│
├── outputs/
│ ├── correlation_heatmap.png
│ ├── confusion_matrix.png
│ └── feature_importance.png
│
└── README.md


---

## 🧮 How to Run

### Clone Repository
```bash
git clone https://github.com/trustanprice/icu-predictions.git
cd icu-predictions
```

---

## 👨🏽‍💻 Author

Trustan Price & Nathan Kereri
📍 University of Illinois Urbana-Champaign
✉️ trustanprice@gmail.com