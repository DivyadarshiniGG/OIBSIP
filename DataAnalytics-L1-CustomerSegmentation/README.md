# Task 2 — Customer Segmentation Analysis

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 1
**Author:** Divyadarshini G G

## Objective
Apply clustering algorithms to segment an e-commerce company's customer base into distinct
groups based on purchasing behaviour (Recency, Frequency, Monetary), enabling targeted
marketing strategies.

## Dataset
- **Source:** Online Retail Dataset (UCI / Kaggle) — transactions from a UK-based online
  gift retailer, Dec 2010–Dec 2011 (sample subset, 3066 transactions, 97 customers after cleaning)
- **Columns:** InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice,
  CustomerID, Country

## Tech Stack
Python, pandas, scikit-learn (KMeans, StandardScaler), matplotlib, seaborn, Jupyter Notebook

## What's in this notebook
1. Load dataset & inspect structure
2. Data cleaning — drop missing CustomerIDs (guest checkouts) and cancelled/returned orders
3. Descriptive statistics — average order value, purchase frequency, customer lifetime value
4. Feature engineering — RFM (Recency, Frequency, Monetary) per customer
5. Feature scaling with StandardScaler
6. Elbow Method to determine optimal number of clusters (K=4)
7. K-Means clustering
8. Cluster visualisation (scatter plots across feature pairs)
9. Cluster profiling — mean RFM values per segment, customer count per segment
10. Marketing recommendations per segment

## Key Insights
- Roughly a third of transactions had no linked CustomerID (guest checkouts) and were
  excluded, since RFM requires customer-level attribution.
- Four distinct customer segments emerged: **Loyal/VIP**, **At-risk/churned**,
  **New/promising**, and **Average/regular** customers — each requiring a different
  marketing approach.
- The clearest business lever is the At-risk segment: customers who spent meaningfully in
  the past but haven't returned recently are the best target for win-back campaigns.

## How to Run
```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
jupyter notebook CustomerSegmentation.ipynb
```

## Files in this folder
- `CustomerSegmentation.ipynb` — full notebook with code, charts, and written observations
- `online_retail_sample.csv` — source dataset
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
All analysis, code structure, cluster interpretation, and written observations in this
notebook are my own independent work, built specifically for this task.
