
# 🧠 Alzheimer's Prediction 

A machine learning-powered web app designed to predict the likelihood of Alzheimer’s disease using clinical, demographic, and cognitive data. Built as part of the DATA 606 Capstone in Data Science at UMBC.

## 📌 Project Overview

Alzheimer’s disease is a progressive neurodegenerative condition that affects memory and cognitive abilities. Early prediction can help with timely intervention. This project develops and deploys a machine learning model that classifies cognitive memory performance based on various health and demographic indicators.

## 📂 Dataset

- **Source**: [National Alzheimer’s Coordinating Center (NACC)](https://naccdata.org/)
- **Size**: 19,209 rows × 58 columns
- **Target**: Memory Score (0.0 to 3.0, where 0 = no impairment, 3 = severe)
- **Features include**:
  - Age, Sex, Years of Education
  - Cardiovascular and Stroke History
  - MMSE Score, Cognitive Assessments
  - Family history, Genetics, Smoking habits

## 🧹 Preprocessing

- Removed 398 duplicate entries
- Imputed missing values using statistical methods
- Dropped columns with >30% missing data
- Reduced features from 58 → 16 based on correlation and relevance
- Created engineered features like:
  - Education-to-Age Ratio
  - Cardiovascular-to-Age Ratio
  - Stroke-to-Decision Ratio

## 📊 Exploratory Analysis

- Visualized distribution of education, age, memory scores
- Used correlation heatmaps to select predictive features
- Found strong positive correlations between MMSE/Cognitive Scores and Memory Score

## 🤖 Models Used

| Model              | Accuracy |
|-------------------|----------|
| Gradient Boosting | **79%**  |
| Random Forest     | 77%      |
| Logistic Regression | 73%    |
| Decision Tree     | 69%      |
| KNN               | 55%      |

**Gradient Boosting** was the best-performing model, tuned using both `GridSearchCV` and `RandomizedSearchCV`.

## 🔍 Hyperparameter Tuning

- Tuned Gradient Boosting: Learning rate = 0.05, Max depth = 3, Estimators = 100
- Tuned Random Forest: Estimators = 300, Split = 10, Criterion = entropy
- Used `k-fold Cross-Validation` for stability: Accuracy avg = 79% with std = 0.01

## 🚀 App Demo

Try the app here: [Live Streamlit App](https://capstone-1-l51c.onrender.com)

### Features:
- Enter patient data (age, education, MMSE, health history, etc.)
- View predicted Memory Score instantly
- Probability score also shown for interpretability

Built using `Streamlit` and deployed on `Render`.

## ⚙️ How to Run Locally

```bash
git clone https://github.com/yourusername/alzheimers-prediction-app.git
cd alzheimers-prediction-app
pip install -r requirements.txt
streamlit run app.py
