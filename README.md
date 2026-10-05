# Week 4 Task: Supervised Learning Model Implementation  
## Breast Cancer Classification (Malignant vs Benign)

This project implements a complete **supervised learning classification pipeline** to predict whether a breast tumor is **malignant** or **benign** using the Wisconsin Breast Cancer (Diagnostic) dataset.

---

## 📋 Objective

- Choose a public medical dataset for binary classification
- Perform data preprocessing and feature engineering
- Train and compare multiple classification models
- Validate using cross-validation
- Evaluate with relevant metrics (Accuracy, Precision, Recall, F1, ROC-AUC)
- Discuss strengths, limitations, and possible improvements

---

## 📊 Dataset

**Wisconsin Breast Cancer (Diagnostic)**  
- Source: UCI Machine Learning Repository (available via `sklearn.datasets`)
- Samples: 569
- Features: 30 numeric features (mean, standard error, and "worst" values of cell nuclei characteristics)
- Target:  
  - `0` → Malignant  
  - `1` → Benign  
- Class distribution: Malignant (212), Benign (357)

---

## 🛠️ Models Used

| Model                  | Description                                      |
|------------------------|--------------------------------------------------|
| Logistic Regression    | Interpretable linear baseline                    |
| Random Forest          | Ensemble of decision trees + feature importance  |
| SVM (RBF Kernel)       | Maximum-margin classifier                        |
| XGBoost                | Gradient boosting (high performance)             |
| Tuned Random Forest    | Hyperparameter-tuned Random Forest via GridSearchCV |

---

## 📈 Key Results (Test Set)

| Model                  | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|------------------------|----------|-----------|--------|----------|---------|
| Logistic Regression    | 0.956    | 0.986     | 0.944  | 0.965    | 0.991   |
| Random Forest          | 0.956    | 0.972     | 0.958  | 0.965    | 0.992   |
| SVM (RBF)              | 0.930    | 0.985     | 0.903  | 0.942    | 0.990   |
| XGBoost                | 0.956    | 0.959     | 0.972  | 0.966    | 0.992   |
| Tuned Random Forest    | 0.956    | 0.972     | 0.958  | 0.965    | 0.992   |

All models achieve **ROC-AUC > 0.99**.

---

## 📁 Project Structure

```
├── Week4_Breast_Cancer_Classification.ipynb   # Main Jupyter Notebook (with XGBoost)
├── Week4_Supervised_Learning_Breast_Cancer_Report.docx  # Detailed Word Report
└── README.md                                  # This file
```

---

## ⚙️ Requirements

Install the required packages:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost
```

Or using a requirements file:

```bash
pip install -r requirements.txt
```

### requirements.txt
```
numpy
pandas
matplotlib
seaborn
scikit-learn
xgboost
```

## 🔍 Pipeline Steps

1. **Data Loading** – Load Wisconsin Breast Cancer dataset
2. **EDA** – Class distribution, correlation analysis, heatmap
3. **Preprocessing**
   - Stratified Train-Test Split (80/20)
   - StandardScaler
   - SelectKBest (top 15 features)
4. **Model Training** – Logistic Regression, Random Forest, SVM, XGBoost
5. **Cross-Validation** – 5-Fold Stratified CV (scoring = ROC-AUC)
6. **Hyperparameter Tuning** – GridSearchCV on Random Forest
7. **Evaluation** – Confusion Matrix, ROC Curve, Classification Report, Feature Importance
8. **Discussion** – Strengths, limitations, and future improvements

---

## 📌 Key Insights

- Features related to **worst perimeter**, **worst radius**, and **concave points** are the most important predictors of malignancy.
- Class imbalance was handled using `class_weight='balanced'` and `scale_pos_weight`.
- All models show excellent and stable performance.

---

## 👤 Author

Yuva Intern – Virtual Data Science Internship  
Week 4 Task: Supervised Learning Model Implementation

---

## 📄 License

This project is for educational purposes.
