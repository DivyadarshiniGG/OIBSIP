# Task 4 — Sentiment Analysis

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 1
**Author:** Divyadarshini G G

## Objective
Build a machine learning model that classifies the sentiment of text data (positive,
negative, or neutral), providing insights into public opinion or customer feedback.

## Dataset
- **Source:** Sampled from a public Twitter entity-sentiment dataset (originally from
  Kaggle: "Twitter Entity Sentiment Analysis")
- **This file:** `twitter_sentiment_sample.csv` — a balanced sample of 3000 tweets
  (1000 each for Positive, Neutral, Negative), deduplicated, with the "Irrelevant" class
  excluded to keep the task scoped to 3-class sentiment as required
- **Columns:** Tweet, Entity (the brand/topic the tweet is about), Sentiment (label)

## Tech Stack
Python, pandas, scikit-learn, NLTK, WordCloud, matplotlib, seaborn, Jupyter Notebook

## What's in this notebook
1. Load dataset & inspect class distribution
2. Text preprocessing pipeline — lowercase, URL/mention/punctuation removal, tokenisation,
   stopword removal
3. Feature extraction using TF-IDF (with explanation of why TF-IDF over raw counts)
4. 80/20 train/test split (stratified)
5. Two classifiers trained: **Multinomial Naive Bayes** and **Logistic Regression**
6. Evaluation — accuracy, precision, recall, F1-score, and confusion matrices for both models
7. Visualisations — sentiment distribution bar chart, WordCloud per sentiment class
8. Error analysis — sample of misclassified tweets with discussion of likely causes
9. Conclusion — model comparison and real-world application

## Results
| Model | Accuracy | Precision | Recall | F1-score |
|---|---|---|---|---|
| Naive Bayes | 0.643 | 0.645 | 0.643 | 0.641 |
| Logistic Regression | 0.632 | 0.636 | 0.632 | 0.632 |

Naive Bayes performed marginally better on this dataset — a reasonable outcome for
short, informal text with many weak individual word signals, where NB's word-independence
assumption matters less.

## Key Insights
- Most misclassifications occur between adjacent sentiment classes (Neutral confused with
  Positive/Negative), not between opposite extremes.
- Both models plateau around 63-64% accuracy, reflecting the real difficulty of 3-class
  sentiment on short, informal tweets — a limitation of bag-of-words style features that
  can't capture sarcasm or word order.

## How to Run
```bash
pip install pandas scikit-learn nltk wordcloud matplotlib seaborn jupyter
python -c "import nltk; nltk.download('stopwords')"
jupyter notebook SentimentAnalysis.ipynb
```

## Files in this folder
- `SentimentAnalysis.ipynb` — full notebook with code, charts, and written observations
- `twitter_sentiment_sample.csv` — dataset used
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
All analysis, code structure, model comparison, and written observations in this notebook
are my own independent work, built specifically for this task.
