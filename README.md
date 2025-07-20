# ML_Classification_Project

📱 Mobile Price Range Prediction - Machine Learning Project
This project focuses on predicting the price range of smartphones using machine learning techniques based on various mobile hardware specifications.

🔍 Problem Statement
The objective is to build a classification model that can predict the price range of mobile phones, categorized into:

0 = Low Cost

1 = Medium Cost

2 = High Cost

3 = Very High Cost

The dataset contains 20 features such as battery power, RAM, screen size, camera specs, and connectivity options (3G, 4G, Wi-Fi).

📦 Dataset Overview
Rows: 2000

Target Variable: price_range (multiclass: 0, 1, 2, 3)

Features:

battery_power, ram, px_height, px_width, blue, dual_sim, four_g, three_g, wifi, touch_screen, etc.

No missing values after preprocessing

Balanced target distribution

🛠️ Technologies & Libraries Used
Python

Pandas, NumPy

Seaborn, Matplotlib, Plotly

Scikit-learn

XGBoost, LightGBM

Imbalanced-learn (SMOTE)

Google Colab

🔄 Workflow Summary
📊 1. Exploratory Data Analysis (EDA)
Visualized target distribution and feature relationships

Used bar charts, line plots, boxplots, and heatmaps

Identified ram, battery_power, and px_width as top correlated features

🧹 2. Data Cleaning
Replaced 0s with NaNs and used KNNImputer

Removed outliers from fc and px_height using IQR filtering

🔬 3. Feature Engineering & Selection
Applied correlation analysis

Focused on key features with highest influence on price

⚖️ 4. Data Balancing (Optional)
Though the target was mostly balanced, SMOTE was applied in some models to simulate class imbalance scenarios

🔎 5. Modeling Techniques
Logistic Regression (Baseline)

Decision Tree Classifier

Random Forest (Base & Tuned with RandomizedSearchCV)

XGBoost Classifier

Voting Ensemble

🔧 6. Hyperparameter Tuning
Used GridSearchCV and RandomizedSearchCV to improve accuracy and reduce overfitting

🧠 Model Evaluation Metrics
Accuracy

Precision

Recall

F1 Score

Confusion Matrix

ROC-AUC (multi-class average)

🏆 Best Performing Models
Model	Train Acc.	Test Acc.	Notes
Logistic Regression (Tuned)	98%	96%	Best generalization
Random Forest (Tuned)	100%	89%	Slight overfitting
Decision Tree (Tuned)	99%	92%	Good, interpretable
XGBoost	100%	91–93%	High performance
Voting Classifier	99%	92%	Ensemble boost

📌 Insights
RAM is the most influential feature followed by battery power and pixel resolution.

Low-cost phones tend to lack features like 4G, Bluetooth, and higher camera specs.

3G-only phones are more likely in lower price tiers.
