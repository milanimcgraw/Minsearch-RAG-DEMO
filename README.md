# MinSearch RAG Demo

This repository demonstrates a lightweight Retrieval-Augmented Generation (RAG) pipeline using [MinSearch](https://github.com/alexeygrigorev/minsearch), a minimalistic search engine that supports efficient keyword-based retrieval and simple appendable indexing. This implementation focuses on exact keyword matching and filter-based search logic in business, finance, and technical datasets.

## ⚙️ Project Structure

Minsearch-RAG/
├── Data/
│   ├── documents.json
│   └── documents-llm.json
├── Notebooks/
│   ├── minsearch-rag.ipynb        # Main RAG demo pipeline (keyword search only)
│   └── parse-faq.ipynb            # FAQ parsing utility
├── minsearch/
│   ├── **init**.py
│   ├── **version**.py
│   ├── append.py
│   ├── minsearch\_example.ipynb    # Interactive example from original repo
│   └── README.md                  # Original author's README
├── src/
│   └── minsearch.py               # Core Index implementation
├── LICENSE
├── README.md                      # ← You are here
├── requirements.txt
└── .gitignore

````

## ⚙️ Features in This Repo

- Keyword-based document filtering using MinSearch's `AppendableIndex`
- Field boosting to prioritize document fields during matching
- Modular pipeline suitable for lightweight or domain-specific business use cases
- Includes example notebooks and sample data for easy customization

> **Note:** This demo focuses on **exact keyword filtering** and does **not** use TF-IDF or cosine similarity for semantic search. If you're interested in lexical or hybrid search demos, check out our other repos.

## ⚙️ Quickstart

Clone the repo and install dependencies:

```bash
git clone https://github.com/milanimcgraw/Minsearch-RAG.git
cd Minsearch-RAG
pip install -r requirements.txt
````

Run the main notebook:

```bash
jupyter notebook Notebooks/minsearch-rag.ipynb
```

## ⚙️ Datasets

This repo includes two JSON sources in the `Data/` folder:

* `documents.json`: Small-scale keyword-only dataset
* `documents-llm.json`: Extended document set with LLM formatting in mind

## ⚙️ Notebooks

* `minsearch-rag.ipynb`: Walkthrough of keyword-based RAG pipeline
* `parse-faq.ipynb`: Script to convert JSON-formatted FAQ content into usable input format

## ⚙️ Dependencies

Dependencies are listed in `requirements.txt`. Key packages:

```text
notebook==7.1.2
pandas
scikit-learn
ipywidgets
tqdm
```

Install with:

```bash
pip install -r requirements.txt
```

## 📌 Credits

> 📦 This project uses [MinSearch](https://github.com/alexeygrigorev/minsearch), created and maintained by **Alexey Grigorev**.
> Licensed under the MIT License.
> Original MinSearch files and examples are preserved in the `/minsearch` directory with attribution.


