# My NLP Lab 10 Submission

**Name:** Maan Ghamdi  
**Student ID:** 2240001433  
**Notebook:** `NLPL10MaanGhamdi2240001433.ipynb`

## What I completed

I answered all four questions about the embedding, encoder, decoder, and softmax layers. I completed the introductory TensorFlow example and implemented an English-to-French LSTM translation pipeline for Task 2. My notebook contains preprocessing, separate training/validation/test sets, model training, learning curves, evaluation, and inference examples, with execution outputs saved inside the notebook.

## How I run my notebook

I use **Python 3.12** and select that Python kernel in Jupyter or VS Code. I choose **Restart Kernel and Run All** to reproduce the whole notebook. The setup cell installs missing packages into the selected kernel. I need internet for the first package installation, and I allow a few minutes for installation and CPU training. I do not need a GPU, a Kaggle login, or an external CSV file.

For a fresh local setup, I run the following commands from a working directory outside my submission folder, with Python 3.12 installed:

```powershell
py -3.12 -m venv lab10-env
.\lab10-env\Scripts\python.exe -m pip install ipykernel
.\lab10-env\Scripts\python.exe -m ipykernel install --user --name lab10 --display-name "Python 3.12 (Lab 10)"
```

I then open the notebook in Jupyter or VS Code, select **Python 3.12 (Lab 10)**, and run all cells. I use a fresh environment to avoid conflicts with packages from other projects. I do not select the system's Python 3.14 kernel for this TensorFlow setup. My tested environment uses Python 3.12.10, TensorFlow 2.20.0, NumPy 2.2.6, pandas 2.3.3, scikit-learn 1.7.2, Matplotlib 3.10.7, NLTK 3.9.2, and Keras 3.15.1.

## My data and method

I used the assigned [English–French dataset by Devicharith on Kaggle](https://www.kaggle.com/datasets/devicharith/language-translation-englishfrench). The source CSV has 175,621 rows. I embedded a compressed, reproducible 4,000-pair sample in the notebook so I can rerun it without downloading data. I documented the filtering and sampling rules beside the data-loading cell.

I use 3,200 training pairs, 400 validation pairs, and 400 test pairs. I keep normalized English sentences unique across splits and fit both tokenizers only on training text. I mask target padding in the loss and accuracy calculation. I train for up to 40 epochs, allow an initial learning period before early stopping, and restore weights selected by validation loss. I report non-padding token accuracy, smoothed corpus BLEU-4, exact sentence match, and actual prediction examples.

## How I interpret my results

I treat this model as a small educational baseline. My general-language sample is not an e-commerce corpus, and a small LSTM can produce inaccurate or incomplete French. I do not claim that the shopping examples are reliable translations or that the model is ready for customer use. I explain these limitations and possible improvements in my notebook. I also distinguish the three-pair introductory demonstration from a meaningful translation benchmark.

I executed all nine code cells from a fresh kernel without errors. In my saved run, the selected epoch was 27, test token accuracy was 19.99%, smoothed BLEU-4 was 0.17/100, and exact sentence match was 0%. These results demonstrate the limitations of my baseline rather than production translation quality.

## My submission files

I include only the solved `.ipynb` notebook and this README. My tables, training logs, plots, and model predictions are stored as notebook outputs. I do not need separate image, model, or dataset files to run the lab. I can view the saved results without retraining; I rerun all cells when I want to regenerate them. Minor numerical differences may occur on different hardware or package versions.
