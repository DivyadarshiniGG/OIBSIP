# Level 2 — Task 4 — Unveiling the Android App Market (Google Play Store Analysis)

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 2
**Author:** Divyadarshini G G

## Objective
Perform a comprehensive data analysis of the Google Play Store ecosystem — cleaning
messy real-world data, exploring app categories, analysing ratings and pricing trends, and
conducting sentiment analysis on user reviews.

## Dataset
- **Source:** Google Play Store Apps dataset (Kaggle)
- **`googleplaystore.csv`:** ~10,800 apps with Category, Rating, Reviews, Size, Installs,
  Type, Price, Content Rating, Genres, etc.
- **`googleplaystore_user_reviews.csv`:** ~64,000 user reviews with pre-labelled
  sentiment (used for validation, not relied on directly)

## Tech Stack
Python, pandas, numpy, matplotlib, seaborn, TextBlob, Jupyter Notebook

## What's in this notebook
1. Load both datasets separately
2. Data cleaning — fixed a real corrupted row (shifted columns), removed duplicates,
   converted `Installs`/`Price`/`Reviews`/`Size` from text to proper numeric types
3. Category analysis — app distribution across categories, most saturated categories
4. Ratings analysis — distribution, average rating by category
5. Size vs. Installs analysis — scatter plot + correlation
6. Pricing analysis — free vs. paid split, price distribution, estimated revenue by category
7. Sentiment analysis on reviews — computed **independently using TextBlob** (not just
   relying on the dataset's pre-existing sentiment labels), then validated against them
8. Sentiment by category — stacked bar chart
9. Conclusion — 3 data-driven insights for a developer planning to launch a new app

## Key Results
- **9658 apps** remained after cleaning (removed 1 corrupted row + duplicates)
- **92.2%** of apps are Free; only 7.8% are Paid
- **92.1% agreement** between our independently-computed TextBlob sentiment labels and
  the dataset's original sentiment labels — validates our sentiment pipeline is capturing
  genuine signal

## Key Insights
1. `FAMILY` and `GAME` are the most saturated categories — hardest to stand out in without
   a strong differentiator.
2. App size has only weak correlation with install count — file size isn't a major driver
   of popularity.
3. Paid-app revenue is concentrated in a handful of categories rather than spread evenly —
   a paid pricing model only makes sense in categories where users already expect to pay.

## How to Run
```bash
pip install pandas numpy matplotlib seaborn textblob jupyter
python -m textblob.download_corpora
jupyter notebook PlayStoreAnalysis.ipynb
```

## Files in this folder
- `PlayStoreAnalysis.ipynb` — full notebook with code, charts, and written observations
- `googleplaystore.csv` — app metadata dataset
- `googleplaystore_user_reviews.csv` — user reviews dataset
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
All analysis, code structure, cleaning decisions, and written observations in this
notebook are my own independent work, built specifically for this task. Sentiment labels
were computed independently rather than copied from the dataset.
