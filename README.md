# 🦠 Pandemic Risk Level Prediction

## 📌 Overview
This project builds a machine learning model to predict whether a disease outbreak is at high or low risk of becoming a pandemic. The dataset includes real patient data from historical outbreaks in China, such as symptoms, hospitalization status, lab test confirmation, and demographic information. The goal is to experiment with different optimization techniques in Neural Networks and compare the results with a baseline ML algorithm (Random Forest).

## 📊 Dataset
- Clinical symptoms: Fever, Cough, Rash, etc.
- Demographics: Age, Gender, Province
- Outcome indicators: Hospitalized, ICU, Lab Confirmed, Quarantined
- Size: ~450 entries
- Task: Binary classification (Pandemic risk: High/Low)

## 🔧 Optimization Results

| Instance | Optimizer | Regularizer | Epochs | Early Stopping | Layers | Learning Rate | Accuracy | Loss   | F1 Score | Precision | Recall |
|----------|-----------|-------------|--------|----------------|--------|----------------|----------|--------|----------|-----------|--------|
| 1        | Default   | None        | 50     | No             | 2      | Default        | 0.99     | 0.4300 | 0.71     | 1.00      | 0.55   |
| 2        | Adam      | L2          | 50     | Yes            | 3      | 0.001          | 0.9778   | 0.0552 | 1.00     | 1.00      | 1.00   |
| 3        | RMSprop   | L1          | 50     | Yes            | 4      | 0.0005         | 1.0000   | 0.0041 | 1.00     | 1.00      | 1.00   |
| 4        | Adam      | L1 + L2     | 60     | Yes            | 3      | 0.0001         | 1.0000   | 0.0116 | 1.00     | 1.00      | 1.00   |
| 5        | Adam      | None        | 60     | Yes            | 3      | 0.0005         | 1.0000   | 0.0070 | 1.00     | 1.00      | 1.00   |

## 🧠 Summary
- **Best model**: Instance 3 (RMSprop, L1, learning rate 0.0005) — perfect performance with the lowest loss.
- **Neural Network vs ML**: Neural Networks, when optimized, outperformed the traditional Random Forest in F1 score and recall.
- **Optimization effects**: Adding early stopping, regularization, and tuning the learning rate significantly improved generalization and reduced overfitting.

## 🔍 Machine Learning Baseline (Random Forest)
- Tuned using `n_estimators` and `max_depth`
- Accuracy: 0.97
- F1 Score: 0.79
- Precision: 0.93
- Recall: 0.67

## 💾 Instructions

### Load and Predict
To load and use the best saved model:
```python
from tensorflow.keras.models import load_model
best_model = load_model("saved_models/model_3.keras")
predictions = best_model.predict(X_test)


youtube Liink: https://youtu.be/V5T25G-mQlc
