# From CNNs to Transformers: A PyTorch Implementation

[![Made with PyTorch](https://img.shields.io/badge/Made%20with-PyTorch-orange?logo=pytorch)](https://pytorch.org/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/YOUR_NOTEBOOK.ipynb)
*(Click the badge above to run the project directly in Google Colab!)*

## 📖 About This Project

This project is a hands-on exploration of four fundamental deep learning architectures. It builds each model to solve a task that highlights its specific strengths and weaknesses.

The goal is to provide a clear, code-first demonstration of *why* different models were invented and *what* kind of problem they are built to solve. We start with a CNN for spatial data, move to a simple RNN for short sequences, show how an LSTM solves the RNN's "forgetting" problem, and finally, implement a Transformer for modern, parallelized sequence processing.

All models are built in **PyTorch** and are designed to be run in the included Google Colab notebook.

---

## 🚀 Models Implemented

1.  **Convolutional Neural Network (CNN)**
    * **Task:** Image Classification
    * **Dataset:** CIFAR-10

2.  **Recurrent Neural Network (RNN)**
    * **Task:** Sequence Classification
    * **Dataset:** "Names by Origin"

3.  **Long Short-Term Memory (LSTM)**
    * **Task:** Sentiment Analysis
    * **Dataset:** IMDB Movie Reviews

4.  **Transformer (Encoder-only)**
    * **Task:** Sentiment Analysis
    * **Dataset:** IMDB Movie Reviews

---

## ⚡ How to Run

The entire project is contained in a single Google Colab notebook (e.g., `Deep_Learning_Models.ipynb`).

1.  Click the **"Open In Colab"** badge at the top of this README.
2.  Once the notebook is open, select a GPU runtime by navigating to **Runtime > Change runtime type > T4 GPU**.
3.  Run the cells sequentially from top to bottom.
4.  All necessary datasets (CIFAR-10, Names, IMDB) will be downloaded automatically by the notebook.

---

## 📊 Final Results & Analysis

This project's main goal is to compare the performance of these models on tasks they were designed for.

### Model Comparison Table

| Model | Task | Dataset | Data Type & Challenge | Best Result (Metric) |
| :--- | :--- | :--- | :--- | :--- |
| **CNN** | Image Classification | CIFAR-10 | **2D Spatial Data:** Finding patterns (edges, shapes) in a grid. | **69.68%** (Val Acc) |
| **RNN** | Sequence Classification | "Names by Origin" | **Short Sequences:** Reading characters one-by-one to find a pattern. | **1.246** (Final Train Loss) |
| **LSTM** | Sentiment Analysis | IMDB Reviews | **Long Sequences:** Understanding context over hundreds of words; avoiding the "forgetting" problem. | **87.72%** (Val Acc) |
| **Transformer** | Sentiment Analysis | IMDB Reviews | **Long Sequences:** Using parallel "attention" to see all words at once. | **81.94%** (Val Acc) |

### Key Takeaways

This table tells a perfect story about the evolution of deep learning:

1.  **CNN:** The specialist for spatial data. Its strength is finding local patterns in a grid (like an image). It's not built for sequential data.

2.  **RNN:** The first step into sequences. It proved it could read a sequence one item at a time (a character) to make a prediction. Its weakness is "forgetting" over long sequences.

3.  **LSTM:** The king of classic NLP. By adding a 'memory cell', it solved the RNN's "forgetting" problem and achieved a high accuracy **(87.72%)** on long text reviews.

4.  **Transformer vs. LSTM:** This is the most interesting result!
    * **LSTM:** 87.72% Acc (in 36 sec/epoch)
    * **Transformer:** 81.94% Acc (in 1m 23s/epoch)

    This teaches us that Transformers are not magic. For a smaller dataset like this, a well-tuned LSTM can be more data-efficient and even outperform a basic Transformer. The Transformer's true power comes from its massive parallelism and ability to scale to *enormous* datasets, which is what powers modern models like GPT and BERT.
