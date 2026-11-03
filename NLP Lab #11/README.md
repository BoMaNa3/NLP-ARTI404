# NLP Lab 11 - Attention with an RNN

I am Maan Ghamdi, student ID 2240001433. I completed both attention tasks in `NLPL11MaanGhamdi2240001433.ipynb`.

## My submission

I included exactly three files: my solved notebook with saved outputs, this README, and the original `Lab_11_QnA_Dataset.csv`. The charts and tables are embedded in my notebook, so I do not need separate output images or a model file.

## How I run my notebook

I keep the notebook and CSV in the same folder. I use Python 3.12 and install the dependencies into the Python environment selected by my notebook editor. My verified package versions are PyTorch 2.15.0 (CPU), pandas 3.1.0, Matplotlib 3.11.2, and ipykernel 7.4.0.

For a new local environment, I open a terminal and run:

```sh
python -m pip install torch==2.15.0 pandas==3.1.0 matplotlib==3.11.2 ipykernel==7.4.0 notebook
```

I then open a terminal in the submission folder and run `python -m notebook`. I open my notebook, select the environment where I installed the packages, and choose **Restart Kernel and Run All Cells**. In VS Code, I can instead open the notebook and select that same Python environment as its kernel. I do not need TensorFlow, a GPU, or Google Colab.

If I use Colab, I upload the notebook, upload the CSV using its Files pane, and run all cells. If a package is missing, I install it with `%pip install torch pandas matplotlib` in a temporary cell and restart the runtime. My saved outputs were verified locally, rather than in Colab.

## What I completed

I lowercased my questions, removed punctuation, built a vocabulary, and padded the token sequences. I corrected the RNN to use `batch_first=True`, cleared gradients before each training step, and masked padding before the attention softmax. I used a fixed seed of 42 and CPU execution for reproducibility.

For Task 1, I plotted three questions, identified their highest-attention words, and explained my observations. For Task 2, I compared "Who programmed you?" and "Who built you?", plotted both attention distributions, and discussed the focus on the creation verbs. I trained for 150 epochs and included a loss curve, predictions, and written answers.

## My verified results

I executed all nine code cells successfully from a fresh Python 3.12.10 kernel. My run used 168 questions and 12 answer groups, achieved 100% training accuracy, and ended at approximately 0.0020 training loss. My checks passed for output shapes, finite values, normalized attention, zero attention on padding, batch independence, padding invariance, and decreasing loss.

I used all questions for training as a classroom attention demonstration. My training accuracy does not establish accuracy on unseen questions. I treat attention as a visualization of learned contextual weights, not a complete causal explanation. Different library versions can change exact numerical results, so I recorded my tested versions above.
