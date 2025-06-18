# 🦠 Pandemic Prediction Using Neural Networks

## 📌 Project Overview

This project applies Neural Network models to predict the likelihood of disease outbreaks escalating into pandemics using clinical and demographic data from China. The dataset includes symptoms, hospitalization status, demographics, and geographic factors. The goal is to identify the best neural network configuration and compare its performance to a traditional machine learning model.

---

## 📊 Dataset Used

- **Source:** Simulated epidemiological dataset from China
- **Key Features:** Age, Gender, Province, Symptoms (Fever, Cough, Rash), Hospitalization status, ICU, Quarantine, Lab confirmation, etc.
- **Target Variable:** Binary classification – risk of pandemic escalation (1) or not (0)

---

## 📈 Optimization Results

| Instance | Optimizer | Regularizer | Epochs | Early Stopping | Layers | Learning Rate | Accuracy | Loss | F1-score | Precision | Recall |
|----------|-----------|-------------|--------|----------------|--------|----------------|----------|------|----------|-----------|--------|
| 1        | Default   | None        | 50     | No             | 2      | Default        | 0.78     | 0.45 | 0.76     | 0.75      | 0.77   |
| 2        | Adam      | L2          | 50     | Yes            | 3      | 0.001          | 0.83     | 0.38 | 0.81     | 0.80      | 0.82   |
| 3        | RMSprop   | L1          | 50     | Yes            | 4      | 0.0005         | 0.86     | 0.31 | 0.84     | 0.85      | 0.84   |
| 4        | Adam      | L1_L2       | 60     | Yes            | 3      | 0.0001         | 0.84     | 0.33 | 0.83     | 0.82      | 0.84   |

---

## ✅ Summary of Findings

- The best performing model was **Instance 3**, which used:
  - **Optimizer:** RMSprop
  - **Regularizer:** L1
  - **Learning Rate:** 0.0005
  - **Dropout:** Yes (0.3)
- It achieved an F1-score of **0.84**, which indicates a strong balance between precision and recall.
- All models benefited from early stopping and regularization, which improved generalization.

---

## 🤖 ML Algorithm vs Neural Network

- A **Random Forest Classifier** was used as the non-Neural ML baseline.
- Despite having competitive accuracy, the Random Forest model achieved a lower F1-score of **0.79**.
- Neural Networks performed better overall due to their ability to capture nonlinear feature interactions and improve with optimization techniques.

---

## 🧠 How to Use the Model

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/pandemic-prediction-model.git
cd pandemic-prediction-model


Youtube Link: https://youtu.be/bCpuGvvRMLA
