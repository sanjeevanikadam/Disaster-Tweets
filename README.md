# Data Preprocessing Script

## Description
This script performs data loading and preprocessing for a dataset, including handling missing values, text cleaning, and lemmatization. It is designed to prepare textual data for machine learning or natural language processing (NLP) tasks.

---

## Features
- Loads a dataset from a CSV file.
- Handles missing values using the `SimpleImputer` class from `sklearn`.
- Cleans text data by:
  - Removing non-alphanumeric characters.
  - Converting text to lowercase.
  - Removing stopwords.
  - Applying lemmatization to reduce words to their base forms.

---

## Dependencies
Ensure the following Python libraries are installed:
- `pandas`
- `nltk`
- `sklearn`
- `re`

To install missing libraries, run:
```bash
pip install pandas nltk scikit-learn

