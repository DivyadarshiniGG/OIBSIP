# Level 2 — Task 1 — Predicting House Prices with Linear Regression

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 2
**Author:** Divyadarshini G G

## Objective
Build and evaluate a linear regression model that predicts house prices based on features
such as area, location, number of rooms, and age/build quality. Develop end-to-end skills
from data cleaning through to model interpretation.

## Dataset
- **Source:** Classic house sales dataset (128 homes), commonly used in statistics/regression
  coursework
- **Columns:** Home (ID), Price, SqFt, Bedrooms, Bathrooms, Offers, Brick (Yes/No),
  Neighborhood (East/North/West)

## Tech Stack
Python, pandas, scikit-learn, matplotlib, seaborn, Jupyter Notebook

## What's in this notebook
1. Load dataset & EDA — null check, descriptive stats, target distribution
2. Feature selection discussion — why each feature was chosen
3. Missing value check & One-Hot Encoding of `Brick` and `Neighborhood`
4. Correlation heatmap
5. 80/20 train/test split
6. Linear Regression model training
7. Evaluation — MSE, RMSE, R² score
8. Actual vs. Predicted scatter plot
9. Residual plot
10. Coefficient analysis — which features drive price up/down
11. Bonus — Ridge & Lasso regularised models compared against plain Linear Regression
12. **Live prediction demo** — a helper function that takes raw house specs (sqft, bedrooms,
    bathrooms, brick, neighborhood) and returns an instant predicted price, so the model's
    real-world use is tangible beyond just test-set metrics

## Results
- **RMSE:** ~$10,685
- **R² Score:** 0.806 — the model explains about 81% of the variance in house price using
  the selected features

## Key Insights
- `SqFt` (square footage) is the strongest driver of house price, consistent with general
  real-estate intuition.
- Neighborhood and brick construction contribute a measurable price premium/discount on
  top of the physical size of the home.
- Ridge and Lasso were tested as a check against overfitting, given the modest dataset size
  (128 rows) relative to the number of encoded features.
 
## How to Run
```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
jupyter notebook HousePricePrediction.ipynb
```

## Files in this folder
- `HousePricePrediction.ipynb` — full notebook with code, charts, and written observations
- `house_prices.csv` — source dataset
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
All analysis, code structure, feature reasoning, and written observations in this notebook
are my own independent work, built specifically for this task. 
