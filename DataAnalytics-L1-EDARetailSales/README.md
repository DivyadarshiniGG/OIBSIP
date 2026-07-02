# Task 1 — EDA on Retail Sales Data

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 1
**Author:** Divya darshini G G

## Objective
Perform a thorough Exploratory Data Analysis (EDA) on a retail sales dataset to uncover
patterns, customer behaviour trends, and actionable business insights.

## Dataset
- **Source:** [Retail Sales Dataset — Kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset)
- **Rows:** 1000 transactions
- **Columns:** Transaction ID, Date, Customer ID, Gender, Age, Product Category,
  Quantity, Price per Unit, Total Amount

## Tech Stack
Python, pandas, matplotlib, seaborn, Jupyter Notebook

## What's in this notebook
1. Data loading & initial inspection (shape, dtypes, null check)
2. Descriptive statistics (mean, median, mode, std)
3. Time series analysis — monthly & quarterly sales trends
4. Customer demographics analysis — age distribution & gender breakdown
5. Product analysis — units sold & revenue by category
6. Correlation heatmap of numerical variables
7. Additional insight — average spend by age group × gender
8. Conclusion — 3 actionable business recommendations

## Key Insights
- Revenue is right-skewed: a small number of high-value transactions pull the average
  transaction value above the median.
- Gender split among customers is close to even; age is broadly distributed rather than
  concentrated in one bracket.
- The product category with the most units sold is not always the one generating the
  most revenue — a signal for margin-aware inventory planning.
- `Total Amount` correlates strongly with `Price per Unit`, while `Age` has very weak
  correlation with spend — age alone doesn't predict transaction value.

## How to Run
```bash
pip install pandas matplotlib seaborn jupyter
jupyter notebook EDA_Retail_Sales.ipynb
```

## Files in this folder
- `EDA_Retail_Sales.ipynb` — full notebook with code, charts, and written observations
- `retail_sales_dataset.csv` — source dataset
- `preview.html` — rendered HTML version of the notebook (for quick viewing without Jupyter)
- `README.md` — this file

## Note on Originality
All analysis, code structure, and written observations in this notebook are my own
independent work, built specifically for this task.
