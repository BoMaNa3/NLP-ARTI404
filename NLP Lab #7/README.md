# NLP Lab 7 — Maan Ghamdi

My name is Maan Ghamdi, and my student ID is **2240001433**. My completed notebook is **NLPL7MaanGhamdi2240001433.ipynb**.

## What I completed

I matched the five NLP tasks to suitable transformer families and explained my choices. I used DistilBERT to print the sentiment label and score for each required sentence, and I used FLAN-T5-small to summarize a short paragraph. I answered the chatbot reflection in four sentences and completed the optional sampling challenge with three generated continuations and an explanation of randomness. I also retained the lab's text-generation, translation, and sentiment examples.

I kept the original task numbering because the supplied lab skips Task 4.

## How I run my notebook

1. I open the notebook in Jupyter with Python 3.11, or upload it to Google Colab with a Python runtime.
2. I start a fresh kernel/session and choose **Run All** to execute the cells from top to bottom.
3. I allow the setup cell to install its dependencies and wait for the three public models to download. I keep internet access available during the first run and allow several minutes for setup.
4. If I previously imported different library versions in the session, I restart the kernel after installation and run all cells again.

I use the CPU explicitly; I do not need a GPU, paid service, API key, or additional data file. I keep enough free disk space and memory for the libraries and model weights. The downloads are cached by Hugging Face outside my submission folder.

I pin Transformers to `4.50.3` and SentencePiece to `0.2.0`; the setup accepts PyTorch `>=2.6,<3`. I use deterministic decoding for the translation and summary. For the optional challenge, I seed once in setup and let the random state advance between samples, so re-running only that cell can change the outputs. I treat the small models' generated text as model predictions, which can be repetitive or imperfect.

## Validation

My notebook was executed from top to bottom in a fresh Python 3.11 environment with Transformers 4.50.3, SentencePiece 0.2.0, and PyTorch 2.6.0 on the CPU. All eight code cells completed without errors, and I included their actual outputs. The three required sentiment predictions were POSITIVE, NEGATIVE, and POSITIVE. The notebook also passed Jupyter notebook-format validation. Download/progress notices in the saved output are informational and did not prevent execution.

I still need a working internet connection for initial setup, compatible dependencies, and sufficient memory when I run it on another machine; the successful test cannot guarantee every possible local environment.

## My submission files

- `NLPL7MaanGhamdi2240001433.ipynb`
- `README.md`
