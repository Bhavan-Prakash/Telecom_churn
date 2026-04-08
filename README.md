# Telecom Churn Prediction (End-to-End ML Pipeline)

This project focuses on building a clean and structured machine learning pipeline to predict customer churn in a telecom dataset.

Instead of just training a model, the goal was to implement a **production-style workflow** using scikit-learn pipelines that handle preprocessing and modeling together.

---

## Why this project?

Customer churn is a real-world business problem.  
Predicting churn early can help companies take action and reduce losses.

This project helped me:
- Work with mixed data types (numerical + categorical)
- Build a reusable ML pipeline
- Understand pitfalls like class imbalance

---

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
  - Pipeline
  - ColumnTransformer
  - LogisticRegression

---

## Pipeline Overview

### Feature Types

- Numerical → `int64`, `float64`
- Categorical → `object`

---

### Preprocessing

**Numerical Pipeline**
- Median Imputation
- StandardScaler

**Categorical Pipeline**
- Most Frequent Imputation
- OneHotEncoder (`handle_unknown="ignore"`)

---

### Combined Pipeline
ColumnTransformer:
├── Numerical Pipeline
└── Categorical Pipeline

Final Pipeline:
→ Preprocessing
→ Logistic Regression Model


---

## Train/Test Strategy

- Train-Test Split: 80/20
- Stratified sampling used to maintain class distribution

---

## Results

### Accuracy

~0.80

### Confusion Matrix

[[38946 0]
[ 9765 0]]


---

### Classification Report

precision recall f1-score

Class 0 → strong performance
Class 1 → not predicted at all


---

## Screenshots (Add your results here)

> Create an `images/` folder in your repo and add screenshots

### Confusion Matrix
![Confusion Matrix](images/confusion_matrix.png)

### Classification Report
![Classification Report](images/report.png)

---

## Key Insight

The model predicts only the majority class (non-churn).

This highlights a **class imbalance problem**, where accuracy becomes misleading.

---

## Learnings

- Importance of using `Pipeline` for clean ML workflows
- Handling mixed data types using `ColumnTransformer`
- Why evaluation metrics like recall and F1-score matter more than accuracy
- Real-world issue of imbalanced datasets

---

## Future Improvements

- Handle imbalance using:
  - `class_weight="balanced"`
  - SMOTE
- Try better models:
  - Random Forest
  - XGBoost
- Perform hyperparameter tuning (GridSearchCV)

---


---

## Suggested Folder Structure

project/
│
├── data/
├── images/
├── notebook/
├── src/
│ ├── preprocessing.py
│ ├── model.py
│
├── main.py
├── requirements.txt
└── README.md


---

## Final Note

This is a baseline model focused on building a clean ML pipeline.  
The current results highlight the importance of handling class imbalance in real-world datasets.

---

## Connect

Feel free to reach out if you have suggestions or want to collaborate.