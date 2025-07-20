# ML_Classification_Project

# 📱 Mobile Price Range Prediction - ML Classification Project

This project predicts the **price range** of a smartphone based on its hardware specifications using **Machine Learning classification models**.

---

## 🗂️ Dataset Overview

- **Source**: Provided internally  
- **Target variable**: `price_range`  
- **Classes**:  
  - 0 = Low Cost  
  - 1 = Medium Cost  
  - 2 = High Cost  
  - 3 = Very High Cost  
- **Features**: 20 technical specs including:
  - `battery_power`, `ram`, `px_height`, `px_width`, `n_cores`, `blue`, `wifi`, `four_g`, `three_g`, `dual_sim`, etc.
- **Balanced classes** (checked using value counts)

---

## 📌 Project Workflow

### 1. 📊 Exploratory Data Analysis (EDA)
- Countplots and histograms to understand feature distributions
- Correlation heatmap to identify redundant features
- Boxplots to detect outliers
- Feature vs price trends using line plots

### 2. 🧹 Data Cleaning & Preprocessing
- Removed duplicates and outliers
- Checked for null values
- Converted data types where necessary
- Encoded binary features as needed

### 3. 🔧 Feature Selection
- Correlation analysis
- Feature importance via Random Forest
- Removed low-variance and redundant features

### 4. ⚖️ Dealing with Imbalance
- Applied **SMOTE (Synthetic Minority Over-sampling Technique)** to balance classes (when needed)

### 5. ⚙️ Feature Scaling
- Applied `StandardScaler` before logistic regression and XGBoost (especially when using SMOTE)

---

## 🤖 Machine Learning Models Used

| Model                      | Description                            |
|---------------------------|----------------------------------------|
| Logistic Regression        | Baseline model                        |
| Decision Tree Classifier   | Simple, interpretable tree model      |
| Random Forest Classifier   | Ensemble of decision trees            |
| Random Forest (Tuned)      | Tuned using GridSearchCV              |
| XGBoost Classifier         | Gradient boosting model               |
| Voting Classifier (Ensemble) | Combines predictions from top models |

---

## 🧪 Model Evaluation

Evaluated using the following metrics:
- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **ROC-AUC Score**
- **Confusion Matrix** (plotted for each model)

---

## 🏆 Best Model Result (Example)

| Model                | Train Acc | Test Acc | F1 Score |
|---------------------|-----------|----------|----------|
| XGBoost Classifier  | 100%      | 93%      | 0.92     |
| Random Forest (Tuned) | 100%    | 91%      | 0.90     |
| Logistic Regression | 98%       | 96%      | 0.95     |

> 📌 Logistic Regression gave the most balanced result with high generalization.

---

## 🧠 Key Insights

- `ram` is the most important predictor of price range.
- Features like `battery_power`, `px_width`, and `px_height` significantly influence prediction.
- Phones without 3G, 4G, Bluetooth, or dual sim tend to be in the low-cost category.
- Misclassifications mostly occurred between neighboring classes (like Medium vs High).

---

## 🚀 How to Run the Project

1. Clone the repo or download the files
2. Install required libraries:
   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn xgboost imbalanced-learn
