# Minsearch RAG Pipeline Demo

## ⚙️ Project Overview          

This repository demonstrates a lightweight Retrieval-Augmented Generation (RAG) pipeline on structured FAQ data using [MinSearch](https://github.com/alexeygrigorev/minsearch), a minimalistic search engine that supports efficient keyword-based retrieval and simple appendable indexing.

## ⚙️ Features

- Keyword-based document filtering using MinSearch's `AppendableIndex`
- Field boosting to prioritize document fields during matching
- Modular pipeline suitable for lightweight or domain-specific business use cases
- Includes example notebooks and sample data for easy customization

## ⚙️ Dependencies

Dependencies are listed in `requirements.txt`. Key packages:

* `pandas`: for handling and structuring JSON data
* `scikit-learn`: for TF-IDF vectorization and cosine similarity
* `ipywidgets`: for interactive controls in Jupyter notebooks
* `tqdm`: for progress tracking
* `notebook`: Jupyter Notebook interface

Install with:

```bash
pip install -r requirements.txt
```

## ⚙️ Datasets

This repo includes two JSON sources in the `Data/` folder:

* `documents.json`: Small-scale keyword-only dataset
* `documents-llm.json`: Extended document set with LLM formatting in mind

## ⚙️ Notebooks

* `minsearch-rag.ipynb`: Walkthrough of keyword-based RAG pipeline
* `parse-faq.ipynb`: Script to convert JSON-formatted FAQ content into usable input format
* `minsearch_example.ipynb`: Example demo from [MinSearch](https://github.com/alexeygrigorev/minsearch) by [**Alexey Grigorev**][https://github.com/alexeygrigorev] 

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

## 📌 Credits

> 📦 This project uses [MinSearch](https://github.com/alexeygrigorev/minsearch), created and maintained by [**Alexey Grigorev**][https://github.com/alexeygrigorev].
> Licensed under the MIT License.
> Original MinSearch files and examples are preserved in the `/minsearch` directory with attribution.

## ⚙️ License

This project is released under MIT license. 


