# Lab 2: Text Preprocessing and Regular Expressions

## Overview

In this lab, I practiced cleaning and preparing text for Natural Language Processing tasks. I used Python regular expressions to search, match, extract, replace, compile, and split text patterns. I also applied common preprocessing techniques with NLTK and spaCy.

To put these techniques into practice, I analyzed an Apple-related Twitter sentiment dataset and extracted its most frequently used hashtags.

## What I Implemented

### Regular Expressions

I worked with Python's `re` module and practiced:

- `re.search()` to locate a pattern anywhere in text
- `re.match()` to check the beginning of a string
- `re.findall()` to return all matches
- `re.sub()` to replace matched text
- `re.compile()` to reuse compiled patterns
- `re.split()` to split text using a pattern
- Anchors, quantifiers, character classes, and sets

### Text Preprocessing

I explored and compared:

- Sentence and word tokenization
- Lowercasing
- Porter and Snowball stemming
- WordNet lemmatization
- Stop-word removal
- Tokenization differences between NLTK and spaCy

### Hashtag Analysis

I loaded Apple-related tweets, converted hashtags to lowercase, extracted them with regex, counted their frequencies, and displayed the ten most common hashtags.

## Results

I extracted **1,616 hashtags** in total. The ten most frequent hashtags were:

| Rank | Hashtag | Frequency |
|---:|---|---:|
| 1 | `#aapl` | 400 |
| 2 | `#apple` | 162 |
| 3 | `#iphone` | 38 |
| 4 | `#december` | 37 |
| 5 | `#iphone6` | 29 |
| 6 | `#stocks` | 15 |
| 7 | `#ipad` | 14 |
| 8 | `#iphone6plus` | 13 |
| 9 | `#iphone6s` | 13 |
| 10 | `#tech` | 12 |

## Tools and Libraries

- Python
- Jupyter Notebook
- `re`
- NLTK
- spaCy
- pandas
- `collections.Counter`

## Setup

```bash
pip install jupyter nltk spacy pandas
python -m spacy download en_core_web_sm
```

Some NLTK features may also require resource downloads such as `punkt`, `punkt_tab`, `wordnet`, and `stopwords`.

## Running the Notebook

1. I clone or download this repository.
2. I install the required libraries and language resources.
3. I open `NLPL2MaanGhamdi2240001433.ipynb`.
4. I run the cells from top to bottom.

The hashtag example reads the Apple Twitter sentiment data directly from an online CSV file, so I need an internet connection when running that section.

## What I Learned

This lab helped me understand how regex and preprocessing work together in an NLP pipeline. I learned that preprocessing choices depend on the task—for example, removing stop words may reduce noise, but removing a word such as *not* can damage sentiment meaning.

## Author

**Maan Abdullah Alghamdi**  
Student ID: `2240001433`
