# Level 2 — Task 2 — Wine Quality Prediction

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 2
**Author:** Divyadarshini G G

## Objective
Train and compare multiple classification models to predict the quality of wine based on
its physicochemical properties such as acidity, density, and alcohol content.

## Dataset
- **Source:** Wine Quality dataset (UCI Machine Learning Repository — Cortez et al., 2009)
- **Rows:** 1599 red wine samples
- **Columns:** fixed acidity, volatile acidity, citric acid, residual sugar, chlorides,
  free/total sulfur dioxide, density, pH, sulphates, alcohol, quality (3-8)

## Tech Stack
Python, pandas, numpy, scikit-learn (Random Forest, SGD, SVC), seaborn, matplotlib, Jupyter Notebook

## What's in this notebook
1. Load dataset & inspect structure — null check, class distribution
2. EDA — feature distributions, correlation heatmap
3. Class imbalance discussion (scores 5/6 dominate; 3/4/8 are rare)
4. Feature engineering — binned quality into Low (3-4) / Medium (5-6) / High (7-8)
5. Stratified train/test split + feature scaling
6. 3 classifiers trained: **Random Forest**, **SGD**, **SVC** (all with `class_weight='balanced'`)
7. Evaluation — accuracy, classification report, confusion matrix for each
8. Feature importance chart (Random Forest)
9. Model comparison table
10. Conclusion — which model is most suitable for deployment, with an honest discussion of
    each model's weaknesses on the minority class
11. **Live prediction demo** — plug in raw wine chemistry, get an instant predicted quality bin

## Results
| Model | Accuracy |
|---|---|
| Random Forest | 0.869 |
| SGD | 0.778 |
| SVC | 0.709 |

## Key Insights
- `alcohol` and `volatile acidity` are the strongest predictors of wine quality —
  consistent with real wine science (higher alcohol correlates with better ratings; high
  volatile acidity gives an unpleasant taste).
- **Important limitation:** despite Random Forest's highest overall accuracy, it scored
  **0% recall on the rare "Low" quality class** — it never correctly flagged a genuinely
  poor wine in testing, defaulting to "Medium" instead. SVC, despite lower overall
  accuracy, caught proportionally more minority-class wines. This is a concrete example of
  why overall accuracy alone can be misleading for imbalanced classification.
- Model choice should depend on the actual business goal: overall correctness (Random
  Forest) vs. catching rare poor-quality wines specifically (SVC, or further tuning with
  techniques like SMOTE).

## How to Run
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook WineQualityPrediction.ipynb
```

## Files in this folder
- `WineQualityPrediction.ipynb` — full notebook with code, charts, and written observations
- `winequality-red.csv` — source dataset
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
All analysis, code structure, model comparison, and written observations in this notebook
are my own independent work, built specifically for this task.
