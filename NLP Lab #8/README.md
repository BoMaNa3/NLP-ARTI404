# NLP Lab 8 — Part-of-Speech Tagging

My name is Maan Ghamdi, and my student ID is 2240001433.

## My submission

I completed the lab in `NLPL8MaanGhamdi2240001433.ipynb`. My submission folder contains only this README and my solved notebook, with the executed outputs saved.

## What I completed

- In Task 1, I identified “play” as `VERB` / `VB` (verb, base form), explained its tag, and printed the text and tags for every token.
- In Task 2, I compared “Google” as a proper noun with “google” as a verb, and “table” as a noun with “table” as a verb. I kept the supplied sentences and noted the typo in the third sentence.
- In Task 3, I displayed both sentences with POS labels and dependency arrows using spaCy's displaCy renderer.

I also retained the teaching examples, added setup for missing packages and language resources, used full-sentence context for NLTK tagging, and included comparative and superlative adjectives in the adjective example. I used the public IPython display API to avoid the visualization import error found during testing.

## How I run my notebook

1. I open the notebook in Jupyter Notebook, JupyterLab, or VS Code with a **Python 3.12** kernel.
2. I choose **Restart Kernel and Run All** (or the equivalent Run All command).
3. I allow the setup cells to finish. My first run needs internet access and permission to install missing Python packages and download the English model and NLTK resources. Later runs reuse the installed resources.
4. I view the printed answers and the diagrams beneath the cells. If my viewer hides saved HTML diagrams, I trust my own notebook and rerun it.

If I need to set up Jupyter locally, I install Python 3.12 and run these commands in a terminal:

```text
py -3.12 -m venv .venv
.venv\Scripts\python -m pip install jupyterlab nltk==3.9.2 spacy==3.8.7
.venv\Scripts\python -m spacy download en_core_web_sm
.venv\Scripts\python -m jupyterlab
```

I create this environment outside my submission folder so that the folder keeps only the two submission files. The `py` commands above are for Windows.

## My validation

I verified all **16 code cells** by executing the notebook from a fresh kernel with **Python 3.12.14**, **NLTK 3.9.2**, **spaCy 3.8.7**, and **en_core_web_sm 3.8.0**. The full run completed without code-cell errors, and both Task 3 diagrams were generated. I checked that the Task 1 and Task 2 outputs agree with my explanations.

I use Python 3.12 for this tested setup; Python 3.14 and other dependency versions were not validated. My first run still depends on internet availability and package-install permissions.
