# Lab 5: Text Representation

Name : Maan A. Alghamdi  
ID : 2240001433

## My work

In this lab, I explored how I can represent text numerically using TF-IDF and Skip-gram Word2Vec. My completed notebook is `NLPL5MaanGhamdi2240001433.ipynb`.

1. **Cosine similarity:** I converted the four supplied sentences into TF-IDF vectors and calculated every pairwise similarity. Sentences 1 and 4 have a similarity of 1.0 because their word counts are identical after tokenization, even though their word order and punctuation differ.
2. **TF-IDF:** I calculated the weights for every word in the three supplied documents and ranked the nonzero scores. With the default settings, `of` and `science` tie for the highest score in the first document, `best` and `courses` tie in the second, and `data` ranks highest in the third. I retained stop words and explained scikit-learn's smoothing and normalization in the notebook.
3. **Word2Vec:** I loaded the supplied Simpsons CSV, selected `spoken_words`, removed missing entries, and applied the lab's cleaning function exactly. I tokenized each dialogue line with NLTK and trained on all nonempty token lists. I used `min_count=1`, `vector_size=100`, `window=5`, and `sg=1`, with five epochs. I added a fixed seed, a stable hash function, and one worker to improve reproducibility.
4. **Similar words:** I used `wv.most_similar()` to show the ten closest words to `homer`, `marge`, and `bart`, including their cosine similarity scores.
5. **Odd words:** I used `wv.doesnt_match()` on all three requested word lists and displayed the model's answers. I interpret these as results learned from dialogue context, rather than fixed facts about the characters.

## How I run my notebook

I keep `simpsons_script_lines.csv` in the same working folder as the notebook. In Google Colab, I upload both files and make sure the CSV is in the runtime's working directory.

If I need the Python packages, I run this in a notebook cell:

```python
%pip install pandas numpy scikit-learn gensim nltk
```

I then restart the kernel and run all cells from top to bottom. I use `word_tokenize(..., preserve_line=True)`, so I do not need to download NLTK's Punkt data. Training time depends on my computer.

## Changes I made to the template

I added my name and ID immediately after the title and completed all five task cells with explanations. I fixed the early missing pandas import and cleared the template's old outputs before executing the completed notebook. Because the separate news dataset was not supplied, I replaced that introductory example with a small, self-contained demonstration corpus and clearly labeled it. My assessed Word2Vec tasks still use the full supplied Simpsons dataset. The original externally hosted illustrations remain in the notebook and need internet access to display.

## What I learned

I found that TF-IDF describes the importance of words within documents, while Word2Vec learns dense word vectors from nearby words. Cosine similarity lets me compare vector directions in both representations. I also learned that a high similarity score does not necessarily mean two sentences have the same meaning or that two words are synonyms. Even with fixed training settings, different library versions can affect Word2Vec results.

## My saved results and verification

I ran every code cell successfully from a fresh kernel and saved the outputs in the notebook. I checked that the cosine similarity matrix is symmetric, its diagonal is 1, and Sentences 1 and 4 have a similarity of 1. I also checked that all requested character names are in the trained vocabulary and that the model uses Skip-gram with 100-dimensional vectors.

I loaded 158,314 CSV rows, excluded 26,459 missing dialogue entries, and trained on 131,839 nonempty tokenized lines. My corpus contained 1,481,008 tokens and 44,175 unique tokens. My odd-word results were `milhouse` for the first group, `nelson` for the second, and `homer` for the third.

I verified this run with Python 3.12.14, pandas 3.0.6, NumPy 2.5.3, scikit-learn 1.9.1, Gensim 4.4.0, and NLTK 3.10.3.
