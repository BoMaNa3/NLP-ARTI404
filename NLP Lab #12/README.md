# NLP Lab 12 — Transformers

**Maan Alghamdi | 2240001433**

I used the DistilBERT example to follow the sentence “The movie was not good.” from tokenization to a sentiment prediction. I then used `bert-base-uncased` to examine how a single attention head processes “Transformers use self-attention to understand language.”

I calculated the total number of heads from BERT’s configuration. Its 12 encoder layers each have 12 heads, giving 144 heads in total. To isolate the second head of the third layer, I selected `result.attentions[2][0, 1]`. The middle index selects the only sentence in my batch.

I read the output one row at a time. For example, I can follow the row for `understand` across to the column for `language` to see how much weight that head gives to `language` at the `understand` position. I included a check that each row sums to one before rounding the displayed weights.

## How I run the lab

I open `NLPL12MaanGhamdi2240001433.ipynb` in Google Colab or Jupyter with a Python 3 kernel and select **Run all**. On the first run, I use an internet connection so the setup cell can install the packages and Hugging Face can download both pretrained models. The final code cell prints the token-labeled attention matrix.
