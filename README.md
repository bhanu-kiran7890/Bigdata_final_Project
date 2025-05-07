# Bigdata_final_Project

---

## Dataset

- Source: [Kaggle Credit Card Fraud Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- Records: 284,807 transactions
- Features: 30 (anonymized), including `Amount`, `Time`, and `Class` (fraud label)

---

## ⚙Technologies Used

- Python (Pandas, Scikit-learn, Matplotlib)
- MongoDB (local)
- Medallion Architecture: Bronze → Silver → Gold

---

## Pipeline Stages

### Bronze Layer: `Bronze.py`
- Reads `creditcard.csv`
- Inserts records into MongoDB `fraud_detection.transactions`

###  Silver Layer: `Silver.py`
- Cleans missing/duplicate records
- Normalizes `Amount`
- Inserts cleaned data into `transactions_cleaned`

### Gold Layer: `Gold.py`
- Plots:
  - Fraud vs Non-Fraud Count
  - Distribution of Amount by Class
- ML Model: Logistic Regression
  - Accuracy and precision metrics printed via `classification_report`

---

## Visual Output

- `fraud_vs_nonfraud.png`
- `amount_distribution.png`

---

## Running the Project

1. Start your local MongoDB server
2. Run each file in this order:

```bash
python Bronze.py
python Silver.py
python Gold.py
