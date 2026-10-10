# Lab 6 — Deep Learning for NLP

Name : Maan A. Alghamdi  
ID : 2240001433

In this lab, I classify Yelp restaurant reviews as negative (0) or positive (1). I compare the provided TF-IDF neural network with a new network that uses Word2Vec review vectors.

## What I completed

- I loaded the 1,000 reviews, cleaned the text, and used a stratified 80/20 split: 800 training reviews and 200 test reviews.
- I corrected the preprocessing indentation so it actually runs and added gradient clearing before each training step.
- I fitted TF-IDF on the training reviews and trained the baseline network.
- For Task 1, I tokenized the reviews and trained skip-gram Word2Vec using only the training reviews, with `vector_size=200`, `window=5`, `min_count=1`, and `sg=1`. I used five Word2Vec training epochs.
- I averaged each review's known word vectors, skipped unseen words, and used a zero vector for reviews without known words. I converted the features and labels to PyTorch tensors.
- For Task 2, I built a `200 → 128 → 64 → 32 → 1` network with ReLU after each hidden layer. I trained it for 15 full-batch epochs using `BCEWithLogitsLoss` and Adam with a learning rate of `0.001`.
- I converted the output logits to probabilities with sigmoid and used a threshold of 0.5. I calculated test accuracy, classification reports, and confusion matrices.

## How I run my notebook

I keep `NLPL6MaanGhamdi2240001433.ipynb` and `07-yelp-dataset.txt` in the same folder. In a Python 3.12 environment, I install the required packages:

```bash
python -m pip install pandas numpy scikit-learn gensim torch jupyter
```

I open the notebook in Jupyter and run all cells from top to bottom with the notebook folder as the working directory. In Google Colab, I upload the notebook and dataset, install any missing packages, and select **Runtime → Run all**.

## My results

I executed all 13 code cells successfully with Python 3.12.14, pandas 3.0.6, NumPy 2.5.3, scikit-learn 1.9.1, Gensim 4.4.0, and PyTorch 2.14.1+cpu. I saved the actual outputs in my notebook.

| Model | Test accuracy |
| --- | ---: |
| TF-IDF baseline | 75.5% |
| Word2Vec with three hidden layers | 49.0% |

My Word2Vec network predicted 198 of the 200 test reviews as negative. Its confusion matrix was `[[98, 2], [100, 0]]`, with actual labels as rows and predicted labels as columns in negative/positive order. Its final training loss was approximately 0.6932, close to the balanced binary chance baseline. I interpret this as poor learning under this configuration, not as a successful sentiment classifier. I retained the requested architecture, learning rate, and 15 epochs instead of tuning against the test set.

## What I learned

I learned how to convert text into numeric features and train a binary classifier with PyTorch. TF-IDF represents word importance, while Word2Vec learns word embeddings from context. Averaging embeddings gives me a fixed-size review vector, but loses word order and can weaken cues such as negation. Learning embeddings from only 800 short reviews also limits their quality.

I keep the test set out of feature fitting and model training. I set random seeds and use one Word2Vec worker to improve repeatability; results may still vary across package versions or platforms. The supplied dataset contains some repeated reviews, so this row-based split is a classroom evaluation rather than a strict duplicate-free benchmark.
