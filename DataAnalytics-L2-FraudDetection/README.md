# Level 2 — Task 3 — Fraud Detection

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 2
**Author:** Divyadarshini G G

## Objective
Build a machine learning pipeline to detect fraudulent financial transactions from a
heavily imbalanced dataset, addressing class imbalance as a core challenge.

## Dataset
- **Source:** Simulated credit card transaction dataset (4900 transactions, 2.04% fraud
  rate), built to mirror the feature structure and imbalance ratio commonly seen in
  real-world fraud detection datasets.
- **Columns:** distance_from_home, distance_from_last_transaction,
  ratio_to_median_purchase_price, transaction_amount, repeat_retailer, used_chip,
  used_pin_number, online_order, is_foreign_transaction, transactions_last_24h, Class
  (0=Genuine, 1=Fraud)

## Tech Stack
Python, pandas, scikit-learn, imbalanced-learn (SMOTE), matplotlib, seaborn, Jupyter Notebook

## What's in this notebook
1. Load dataset & analyse class imbalance (2.04% fraud)
2. EDA — transaction amount & distance-from-home patterns by class
3. Discussion of why accuracy is a misleading metric for imbalanced fraud data
4. SMOTE oversampling applied to the **training set only** (test set stays realistic)
5. 2 classifiers trained: **Logistic Regression** and **Random Forest**
6. Evaluation — Precision, Recall, F1-score, AUC-ROC, confusion matrices, ROC curve
7. Discussion of the Recall vs. Precision trade-off and which matters more for fraud
8. Feature importance chart (Random Forest)
9. Scalability discussion — how this would handle 1M transactions/hour
10. **Live prediction demo** — plug in transaction details, get an instant fraud/genuine prediction with probability

## Results
| Model | Precision | Recall | F1 | AUC-ROC |
|---|---|---|---|---|
| Logistic Regression | 0.40 | **0.95** | 0.57 | 0.977 |
| Random Forest | 0.57 | 0.65 | 0.61 | 0.976 |

## Key Insights
- Logistic Regression catches nearly all fraud (95% recall) but with many false alarms
  (40% precision); Random Forest is more balanced but misses more fraud.
- Since missing real fraud is typically costlier than a false alarm, **Logistic
  Regression's higher recall makes it the stronger first-pass filter**, assuming a manual
  review step exists to absorb its false positives.
- `ratio_to_median_purchase_price` and `distance_from_home` are the strongest fraud
  indicators — consistent with how real fraud detection systems flag "unusual for this
  customer" behaviour.

## How to Run
```bash
pip install pandas scikit-learn imbalanced-learn matplotlib seaborn jupyter
jupyter notebook FraudDetection.ipynb
```

## Files in this folder
- `FraudDetection.ipynb` — full notebook with code, charts, and written observations
- `credit_card_transactions.csv` — dataset used
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
The dataset, modelling approach, evaluation, and all written discussion in this notebook
are my own independent work, built specifically for this task.
