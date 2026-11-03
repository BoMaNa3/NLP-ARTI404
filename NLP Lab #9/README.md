# NLP Lab 9 — Maan Ghamdi

**Student ID:** 2240001433  
**Notebook:** `NLPL9MaanGhamdi2240001433.ipynb`

## My work

I completed all three tasks using spaCy. I identify entities in a sentence entered by the user and print their labels, explanations, token positions, and character positions. I inspect the supplied legal paragraph, add missing entities or correct incomplete spans, count the people and organizations, and display the highlighted entities. My corrected paragraph contains **1 PERSON** and **2 ORG** entities.

I create the Microsoft training example with `Example.from_dict()`, check annotation alignment, and fine-tune a separate English NER pipeline for exactly **20 iterations**. I save it in a folder named `custom_ner_model`, reload it, and identify entities in a test sentence. I also check that saving and reloading preserves the predictions. I use a temporary parent directory and clean it up afterward so my submission contains only this README and the notebook. Rerunning the notebook recreates the model automatically.

I fixed the original visualization cell, which attempted to load a model before it had been trained. I also repaired the broken quotation marks in the task text. My notebook includes saved text outputs and entity visualizations.

## How I run my notebook

1. I open the notebook in Jupyter Notebook, JupyterLab, VS Code, or Google Colab. For a local installation, I recommend a **Python 3.12** kernel.
2. I restart the kernel and run all cells from top to bottom. The setup cell installs spaCy and the English model if they are missing. I need internet access and permission to install packages on the first run.
3. When Task 1 asks for a sentence, I type my sentence and press Enter. I can press Enter without typing to use the provided sample. Automated execution without interactive input uses the sample and explicitly reports that choice.
4. I view the text results and highlighted entities directly in the notebook. If my viewer blocks saved HTML, I trust this notebook or rerun its visualization cells.

I tested every code cell successfully on **Python 3.12.10**, using **spaCy 3.8.7** with **en_core_web_sm 3.8.0**. I also checked the typed-input path. My setup pins **typer 0.12.5** and **click 8.1.8** to prevent a dependency import error. If my environment already has another spaCy major/minor version, I run `%pip install spacy==3.8.7` in a notebook cell, restart the kernel, and run all cells again. A restricted or offline environment needs these dependencies installed beforehand.

## What my results mean

I distinguish manually corrected entities in Task 2 from the pretrained model's original predictions by displaying both. In Task 3, I train on only the supplied paragraph. My rearranged test sentence demonstrates prediction after reloading; it does not measure general accuracy on independent data. I would need more varied annotated text and held-out examples for a reliable evaluation.

I use zero-based offsets with an exclusive end position: `[start, end)`.

## Reference

I followed the [spaCy training documentation](https://spacy.io/usage/training#ner) for training examples and model updates.
