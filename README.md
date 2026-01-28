📌 Project Structure
The project is divided into two main parts:
    Dataset 1 – Classification: Predicting accident injury severity
    Dataset 2 – Regression: Predicting biological growth parameters
    
Each task follows a full machine learning pipeline from data exploration to final evaluation.

🚦 DATASET 1: Injury Severity Classification
🎯 Objective
The goal of this task is to predict injury severity in road accidents using the FARS (Fatality Analysis Reporting System) accident dataset.
This is a classification problem where the target variable represents the level of injury severity. Due to class imbalance, special care was taken in model evaluation and training.

🔍 Exploratory Data Analysis (EDA)
1. Dataset contains 100,000+ accident records
2. Mixture of numerical and categorical features
3. No major missing value issues
4. The target variable showed class imbalance, with non-severe injuries occurring more frequently

EDA included:
1. Distribution plots
2. Target class frequency analysis
3. Summary statistics
4. Correlation and feature behavior analysis

⚙️ Data Preprocessing
A robust preprocessing pipeline was built using Scikit-learn Pipelines and ColumnTransformer.
1. Numerical Features
   - Missing values handled using median imputation
   - Features scaled using StandardScaler

2. Categorical Features
   - Missing values filled using most frequent value
   - Encoded using One-Hot Encoding
   - Unknown categories handled safely during testing

3. This ensured:
   - No data leakage
   - Consistent transformations across models

🧪 Experimental Design
   - Data split into 80% training and 20% testing
   - Stratified sampling used to preserve class distribution
   - Stratified 5-fold cross-validation applied on training data

🤖 Classification Models Implemented
   Four ML pipelines were developed, each combining preprocessing with a different classifier:
1. Logistic Regression (with class weighting)
2. K-Nearest Neighbours (KNN)
3. Decision Tree
4. Random Forest

📊 Evaluation Metrics
Because of class imbalance, multiple metrics were used:
Accuracy: 
Weighted F1-score (primary metric)

🏆 Results

Among all models tested, Logistic Regression achieved the best balance between performance and generalisation on the test set.

Key Takeaways:

- Simpler linear models performed competitively
- Class weighting helped handle imbalance
- Complex models did not significantly outperform Logistic Regression
