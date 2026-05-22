 🏦 Banking Customer Churn Prediction
 ChurnZero Hackathon 2025 | Round 2 Submission



![Python](https://img.shields.io/badge/Python-3.10-blue)




![XGBoost](https://img.shields.io/badge/Model-XGBoost-green)




![ROC-AUC](https://img.shields.io/badge/ROC--AUC-0.9999-brightgreen)




![Status](https://img.shields.io/badge/Status-Complete-success)



---

 🎯 Problem Statement
In the competitive banking sector, customer churn is a silent revenue killer. This project builds an end-to-end ML pipeline to identify customers at high risk of churning — enabling the bank to take proactive retention actions before it's too late.

> Business Impact:Acquiring a new customer costs 5x more than retaining one. Predicting churn with high accuracy directly translates to revenue saved.

---

📊 Dataset Overview

| Property | Details |
|----------|---------|
| Training Samples | 8,101 customers |
| Test Samples | 2,026 customers |
| Total Features | 97 behavioral & demographic signals |
| Target Variable | `churn` (0 = Retained, 1 = Churned) |
| Class Distribution | 84% Retained vs 16% Churned |

---

🔍 Key Insights from EDA

| Feature | Churn Correlation | Business Insight |
|--------|-------------------|-----------------|
| `total_digital_logins` | 0.508 | Low engagement = higher churn risk |
| `unresolved_complaint_count` | 0.494 | Unresolved issues drive customers away |
| `customer_feedback_sentiment` | 0.458 | Negative sentiment is an early warning |
| `balance_decline_percentage` | 0.456 | Declining balance = disengagement |
| `complaint_resolution_time` | 0.448 | Slow resolution frustrates customers |

---

⚙️ ML Pipeline

```
Raw Data → Data Cleaning → Feature Engineering → Model Training → Evaluation → Predictions
```

1. Data Cleaning— Median imputation for missing values
2. Feature Engineering — Dropped high-cardinality ID columns, Label encoded categoricals
3. Model Training — XGBoost with class imbalance handling
4. Evaluation — ROC-AUC, F1-Score, Precision, Recall
5. Predictions — Generated predictions.csv for 2,026 customers

---

 🤖 Model: XGBoost Classifier

Why XGBoost?
- Handles class imbalance via `scale_pos_weight`
- Built-in regularization prevents overfitting
- Captures complex non-linear relationships
- Industry standard for tabular classification tasks

Hyperparameters:
```python
XGBClassifier(
    n_estimators=200,
    max_depth=4,
    learning_rate=0.05,
    subsample=0.8,
    colsample_bytree=0.8,
    scale_pos_weight=5,
    min_child_weight=5
)
```

---

📈 Model Performance

| Metric | Score |
|--------|-------|
| ROC-AUC | 0.9999 |
| Accuracy | 100% |
| Precision (Churn) | 1.00 |
| Recall (Churn) | 0.99 |
| F1-Score (Churn) | 0.99 |

---

 🏆 Top Churn Risk Factors

```
Total Digital Logins          ████████████████  0.508
Unresolved Complaint Count    ███████████████   0.494
Customer Feedback Sentiment   ██████████████    0.458
Balance Decline Percentage    ██████████████    0.456
Complaint Resolution Time     █████████████     0.448
```

---

💡 Business Recommendations

1. 🚨 Alert System — Flag customers with 3+ unresolved complaints immediately
2. 💬 Proactive Outreach — Contact customers showing negative sentiment scores
3. 💰 Retention Offers — Target customers with declining balances with special offers
4. 📱 Digital Re-engagement— Re-activate customers with low app login counts
5. ⚡ Fast Resolution — Resolve all complaints within 24 hours to reduce churn risk

---

 🚀 How to Reproduce

```bash
# Step 1: Open churn_notebook.ipynb in Google Colab
# Step 2: Upload ChurnZero_dataset_v1.csv and ChurnZero_test_v1.csv
# Step 3: Run all cells in order
# Step 4: predictions.csv will be auto-generated
```

---

📁 Repository Structure

```
churnzero-banking-churn/
├── 📓 churn_notebook.ipynb    # Complete ML pipeline
├── 📊 predictions.csv         # Final test predictions
└── 📖 README.md               # Project documentation


---

🛠️ Tech Stack
Python • XGBoost • Scikit-learn • Pandas • NumPy • Google Colab

---
*Built with ❤️ for ChurnZero Hackathon 2025*
