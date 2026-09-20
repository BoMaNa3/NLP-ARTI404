# Lab 3: N-Gram Language Models

## Overview

In this lab, I explored unigram, bigram, and trigram language models. I generated n-grams, added sentence-boundary padding, calculated counts and conditional probabilities, trained Maximum Likelihood Estimation (MLE) models, generated text, and evaluated language models with perplexity.

I then applied these concepts to three datasets: tweets, IMDB movie reviews, and poems.

## What I Implemented

### N-Gram Foundations

I used NLTK to:

- Generate unigrams, bigrams, and trigrams
- Add `<s>` and `</s>` sentence-boundary padding
- Count word and n-gram frequencies
- Estimate conditional probabilities
- Train an MLE bigram model
- Predict a following word from its context
- Evaluate a model using perplexity
- Build a trigram model from the Reuters corpus and generate text

### Part 1: Tweet Generation

I cleaned a large collection of anonymous tweets by removing:

- Mentions and hashtags
- `RT` markers
- URLs
- Emojis
- Punctuation, digits, and non-Latin characters
- Extra spaces

After cleaning, I tokenized the tweets and trained bigram and trigram language models. I used the bigram model to generate sample tweets and compared MLE evaluation with Laplace smoothing.

### Part 2: IMDB Review Analysis

I processed 50,000 movie reviews by removing HTML, converting text to lowercase, tokenizing it, removing punctuation, and filtering English stop words. I then calculated review statistics and plotted the 20 most frequent words.

### Part 3: Poem Bigram Analysis

I preprocessed a poem classification dataset, generated bigrams, counted their frequencies, displayed the ten most common bigrams, and visualized them in a horizontal bar chart.

## Key Results

### Tweet Model

- Original tweets: **202,151**
- Tweets remaining after cleaning: **143,293**
- Total tokens: **2,182,936**
- Vocabulary size: **76,195**
- Count of `pakistan`: **14,010**
- Count of `pakistan is`: **699**
- Count of `pakistan is a`: **70**
- `P(is | pakistan)`: **0.0499**
- `P(a | pakistan is)`: **0.1001**
- Sample-sentence perplexity: **34.19**
- Perplexity on the first 1,000 corpus tweets: **100.89**
- Held-out MLE perplexity: **infinite** because unseen bigrams receive zero probability
- Held-out Laplace perplexity: **4,723.85**

### IMDB Reviews

- Total reviews: **50,000**
- Average words per review: **228.53**
- Average words after stop-word removal: **114.88**
- Reviews containing `good`: **18,702**
- Reviews containing `bad`: **11,641**
- Most frequent content word: `movie` with **86,642** occurrences

### Poems

- Dataset rows after removing empty poems: **837**
- Total bigrams: **20,000**
- Unique bigrams: **18,335**
- Most frequent bigram: `let us` with **10** occurrences

## Datasets

I used the following datasets:

- [Anonymous – Random Tweets](https://www.kaggle.com/datasets/adizafar/large-random-tweets-from-pakistan)
- [IMDB Dataset of 50K Movie Reviews](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)
- [Poem Classification (NLP)](https://www.kaggle.com/datasets/ramjasmaurya/poem-classification-nlp)
- The Reuters corpus included with NLTK

I place the downloaded CSV files at the paths expected by the notebook:

```text
data/
├── tweets/
│   └── Random Tweets from Pakistan- Cleaned- Anonymous.csv
├── imdb/
│   └── IMDB Dataset.csv
└── poem/
    └── Poem_classification - train_data.csv
```

## Tools and Libraries

- Python
- Jupyter Notebook
- NLTK
- pandas
- Matplotlib
- emoji
- `re`
- `collections.Counter` and `defaultdict`

## Setup

```bash
pip install jupyter nltk pandas matplotlib emoji
```

The notebook downloads the required NLTK resources, including Reuters, Punkt, Punkt Tab, and the English stop-word list.

## Running the Notebook

1. I clone or download this repository.
2. I install the required libraries.
3. I download the three CSV datasets and place them in the directory structure shown above.
4. I open `NLPL3MaanGhamdi2240001433.ipynb`.
5. I run the cells from top to bottom.

## What I Learned

This lab showed me how n-gram models learn local word patterns and use them to estimate probabilities or generate new text. I also saw the main limitation of unsmoothed MLE models: a single unseen n-gram can make held-out perplexity infinite. Laplace smoothing avoids zero probabilities, although its perplexity can still be high when the vocabulary is large.

## Author

**Maan A. Alghamdi**  
Student ID: `2240001433`
