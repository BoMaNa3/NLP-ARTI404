# NLP Lab 4: Classification and Evaluation

Name : Maan A. Alghamdi  
ID : 2240001433

In this lab, I classified Amazon mobile phone reviews as positive, negative, or neutral. I cleaned the text using five preprocessing steps, removed duplicate reviews, and split the data into 80% training and 20% testing.

I extracted TF-IDF features and trained a Multinomial Naive Bayes classifier. I evaluated it using accuracy, precision, recall, F1-score, and a confusion matrix. My model achieved **82.82% test accuracy**, but struggled to identify neutral reviews.

To run my solution, open `NLPL4MaanGhamdi2240001433.ipynb` and execute the cells under **Completed solution** in order. It requires `pandas`, `scikit-learn`, and `matplotlib`. The notebook attempts to download the Amazon dataset if the CSV is not available locally.
