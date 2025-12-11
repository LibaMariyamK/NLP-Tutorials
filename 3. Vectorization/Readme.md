# Vectorization and Word Embeddings in NLP

This folder contains notebooks demonstrating different **text vectorization** and **word embedding** techniques in NLP (Natural Language Processing).

---

## 1. Introduction

In NLP, machines cannot understand text directly. To process text, we convert words or documents into **numbers or vectors**. This process is called **vectorization**.

**Why vectorization?**

* It allows mathematical operations on text.
* Enables ML models to understand patterns in language.

There are two main approaches:

### A. Sparse Representations

* Represent text as vectors where most elements are **zero**.
* Examples: **Bag-of-Words (BoW), TF-IDF**
* **Characteristics:**

  * Each word is independent; no notion of similarity.
  * Vector size = vocabulary size → can be very large.
  * Simple and fast for smaller datasets.
* **Pros:** Easy to implement, interpretable.
* **Cons:** Large memory, cannot capture meaning or similarity between words.

### B. Dense Representations (Word Embeddings)

* Represent words as **dense vectors** with smaller dimensions.
* Examples: **Word2Vec, GloVe, FastText**
* **Characteristics:**

  * Each word has a vector of fixed size (e.g., 100-300).
  * Captures similarity between words (`king` ≈ `queen`).
  * Learned from word co-occurrence or prediction tasks.
* **Pros:** Captures semantic meaning, smaller vector size.
* **Cons:** Static embeddings don’t change with context.

---

## 2. Static vs Contextual Embeddings

| Type           | Description                                          | Examples                      |
| -------------- | ---------------------------------------------------- | ----------------------------- |
| **Static**     | Each word has a single vector regardless of context. | Word2Vec, GloVe, FastText     |
| **Contextual** | Word vectors change based on surrounding words.      | BERT, RoBERTa, GPT embeddings |

**Static embeddings** are simple and fast but cannot handle multiple meanings of a word (e.g., `bank` as river vs finance).
**Contextual embeddings** are powerful, handle polysemy, but are computationally heavier.

---

## 3. Notebooks in this Folder

| Notebook            | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| `1_BoW.ipynb`      | Bag-of-Words vectorization – counts word occurrences in text. |
| `2_TFIDF.ipynb`    | TF-IDF – weighs words by importance in documents.             |
| `3_Word2Vec.ipynb` | Word2Vec embeddings – learns word similarity from context.    |
| `4_GloVe.ipynb`    | GloVe embeddings – uses global co-occurrence statistics.      |
| `5_BERT.ipynb`    | BERT embeddings – generates context-aware word representations. |


> These notebooks demonstrate how to apply each method on sample text and compare results.

---

## 4. Summary / Key Points

* **Sparse vs Dense:** Sparse is simple, dense captures meaning.
* **Static vs Contextual:** Static is fixed, contextual changes with sentence.
* **Choosing method:**

  * Small datasets or interpretable models → BoW/TF-IDF.
  * Semantic understanding or similarity tasks → Word2Vec/GloVe/FastText.
  * Context-sensitive tasks (Q&A, NLP pipelines) → BERT/RoBERTa.
* **Limitations:**

  * Sparse vectors → memory-heavy, no semantics.
  * Static embeddings → cannot understand word in context.
  * Contextual embeddings → computationally heavy, require GPUs for large data.

---

