# Level 2 — Task 5 — Autocomplete and Autocorrect Data Analytics

**Internship:** Oasis Infobyte SIP
**Track:** Data Analytics
**Level:** 2
**Author:** Divyadarshini G G

## Objective
Analyse the efficiency and accuracy of autocomplete and autocorrect algorithms using NLP
techniques. Implement and compare multiple approaches for text prediction and spelling
correction on a real text dataset.

## Dataset / Corpus
- **Source:** *Alice's Adventures in Wonderland* by Lewis Carroll — full public domain
  text (via Project Gutenberg / GITenberg), ~29,000 words
- Used as the training corpus for both the autocomplete (n-gram) and autocorrect
  (frequency + edit-distance) models

## Tech Stack
Python, pandas, NLTK, pyspellchecker, collections, matplotlib, Jupyter Notebook

## What's in this notebook
1. Load and clean the text corpus (strip Project Gutenberg header/footer)
2. NLP preprocessing — tokenisation, lowercasing, punctuation removal
3. Word frequency visualisation (top 20 most frequent words)
4. Autocomplete — frequency-based **bigram and trigram** models, tested on 10 input prefixes with top-3 predictions each
5. Autocomplete evaluation — precision/recall via top-3 hit rate on held-out sequence
6. Autocorrect — edit-distance based correction, tested on 20 deliberately misspelled words
7. **Two autocorrect approaches compared**: PySpellChecker vs. a custom Levenshtein-distance implementation
8. Confusion matrix showing correct/incorrect corrections
9. Discussion of limitations vs. production systems (Google Keyboard, etc.)
10. **Live prediction demo** — type a prefix or misspelled word, get an instant autocomplete/autocorrect result

## Results
- **PySpellChecker autocorrect accuracy:** 90.0%
- **Custom Levenshtein autocorrect accuracy:** 85.0%
- Bigram vs. trigram autocomplete compared via top-3 hit rate on held-out text

## Key Insights
- PySpellChecker slightly outperforms a raw Levenshtein-distance approach because it
  combines edit distance with word frequency weighting, favouring common words when
  multiple candidates are equally close in edit distance.
- The n-gram autocomplete models are limited by corpus size — many realistic prefixes
  never appeared in this ~29,000-word book, so they have zero predictions (a sparsity
  problem that scales down with larger corpora).
- Both algorithms are fundamentally different from production systems (Google Keyboard),
  which use neural language models, personalisation, and vastly larger training corpora.

## How to Run
```bash
pip install pandas nltk pyspellchecker matplotlib jupyter
python -c "import nltk; nltk.download('punkt')"
jupyter notebook AutocompleteAutocorrect.ipynb
```

## Files in this folder
- `AutocompleteAutocorrect.ipynb` — full notebook with code, charts, and written observations
- `alice_in_wonderland.txt` — text corpus used
- `preview.html` — rendered HTML version (for quick viewing without Jupyter, not required for GitHub)
- `README.md` — this file

## Note on Originality
All analysis, code structure, algorithm comparison, and written observations in this
notebook are my own independent work, built specifically for this task. The text corpus
itself is a public domain literary work (Project Gutenberg), used only as training data.
