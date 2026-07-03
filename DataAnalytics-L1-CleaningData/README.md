# Task 3 — Cleaning Data

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 1
**Author:** Divyadarshini G G

## Objective
Demonstrate professional-level data cleaning skills by taking a deliberately messy dataset
and systematically transforming it into a clean, analysis-ready dataset, with every
decision documented.

## Dataset
- **Source:** Synthetically generated customer transaction dataset (625 rows), built
  specifically for this task to contain realistic data quality issues.
- **Deliberate issues included:** missing values across 6 columns, 25 exact duplicate
  rows, inconsistent text casing/whitespace (`"male"`, `"MALE"`, `"  PRIYA DAS  "`),
  4 different date formats mixed in one column, numeric columns stored as text with stray
  characters (`"48.0 yrs"`, `"$186.12"`), and injected outliers (e.g., Age = 999, negative
  purchase amounts).

## Tech Stack
Python, pandas, numpy, Jupyter Notebook

## What's in this notebook
1. Data quality report — nulls, duplicates, dtype issues
2. Missing data handling — per-column strategy (median/mode imputation, row deletion, or
   intentional no-fill), each justified
3. Duplicate removal
4. Standardisation — text casing/whitespace, mixed date formats unified via `format='mixed'`
5. Outlier detection using the IQR method, with capping/correction decisions explained
6. Data type correction (`object` → `int`/`float`/proper `datetime`)
7. Before vs. after summary table
8. Save the cleaned dataset to `cleaned_customer_data.csv`

## Key Decisions & Reasoning
- **Age, PurchaseAmount** → median imputation (skew-resistant) for missing values;
  physically impossible values (Age > 90, negative purchases) treated as entry errors and
  capped/corrected rather than dropped, to preserve the rest of each row's valid data.
- **Gender, Country** → mode imputation after first standardising casing, since these are
  low-cardinality categorical fields.
- **SignupDate** → rows with missing dates were dropped, since a date can't be reasonably
  inferred.
- **Email** → left missing intentionally; a unique identifier shouldn't be fabricated and
  isn't required for the numeric analysis this dataset supports.

## How to Run
```bash
pip install pandas numpy jupyter
jupyter notebook CleaningData.ipynb
```

## Files in this folder
- `CleaningData.ipynb` — full notebook with code, data quality report, and written justification for each cleaning decision
- `messy_customer_data.csv` — original messy dataset
- `cleaned_customer_data.csv` — final cleaned output
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
The dataset, cleaning strategy, code, and all written justifications in this notebook are
my own independent work, built specifically for this task.
