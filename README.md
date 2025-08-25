# 💳 Credit Card Fraud Detection System Using Machine Learning 🚨

## 🎯 Project Overview
This project aims to build a **Credit Card Fraud Detection System** using Machine Learning to detect fraudulent transactions among a large set of legitimate ones.  

- **Problem Type:** Binary Classification (0 → Legitimate, 1 → Fraud)  
- **Dataset:** Credit Card Transactions Dataset (Kaggle)  
- **Challenge:** Extremely imbalanced dataset (~0.17% fraud)

---

## 🗂 Dataset Description
The dataset contains:

| Feature | Description |
|---------|-------------|
| Time    | Seconds elapsed since first transaction |
| V1–V28  | PCA-transformed features for privacy |
| Amount  | Transaction amount |
| Class   | Target (0 = Legitimate, 1 = Fraud) |

**Class distribution:**

- ✅ Legitimate: 284,315 (~99.83%)  
- ⚠️ Fraudulent: 492 (~0.17%)  

💡 **Insight:** Dataset is highly imbalanced, so special handling is required.

---

## 🛠 Data Preprocessing
1. **Balancing the dataset:**  
   - All fraudulent transactions included  
   - Equal number of legitimate transactions sampled  
   - Result: 492 legitimate + 492 fraud  

2. **Train-Test Split:**  
   - 80% training, 20% testing  
   - Stratified split to maintain class ratio  

3. **Feature Scaling:** Standardized `Amount` and `Time` (if required)

---

## 🤖 Model Training
**Algorithm:** Logistic Regression  

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()
model.fit(X_train, Y_train)
Y_pred = model.predict(X_test)
```
---
## 🤖 Model Result

**✅ Accuracy Score:** `96.95%`  

**📊 Confusion Matrix:**

|               | Predicted Legit ✅ | Predicted Fraud ⚠️ |
|---------------|-----------------|------------------|
| Actual Legit ✅  | 98            | 1               |
| Actual Fraud ⚠️ | 5             | 93               |

<img width="626" height="584" alt="image" src="https://github.com/user-attachments/assets/a1170249-50fe-4e98-ba22-b639b9a94598" />

