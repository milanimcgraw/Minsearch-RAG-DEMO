## Installation 

```bash
pip install minsearch
```

## Environment setup

To run it locally, make sure you have the required dependencies installed:

```bash
pip install pandas scikit-learn
```

Alternatively, use pipenv:

```bash
pipenv install --dev
```

## Usage

### Basic Search with Index

```python
from minsearch import Index

# Create documents
docs = [
    {
        "question": "How do I join the course after it has started?",
        "text": "You can join the course at any time. We have recordings available.",
        "section": "General Information",
        "course": "data-engineering-zoomcamp"
    },
    {
        "question": "What are the prerequisites for the course?",
        "text": "You need to have basic knowledge of programming.",
        "section": "Course Requirements",
        "course": "data-engineering-zoomcamp"
    }
]

# Create and fit the index
index = Index(
    text_fields=["question", "text", "section"],
    keyword_fields=["course"]
)
index.fit(docs)

# Search with filters and boosts
query = "Can I join the course if it has already started?"
filter_dict = {"course": "data-engineering-zoomcamp"}
boost_dict = {"question": 3, "text": 1, "section": 1}

results = index.search(query, filter_dict=filter_dict, boost_dict=boost_dict)
```

### Incremental Search with AppendableIndex

```python
from minsearch import AppendableIndex

# Create the index
index = AppendableIndex(
    text_fields=["title", "description"],
    keyword_fields=["course"]
)

# Add documents one by one
doc1 = {"title": "Python Programming", "description": "Learn Python programming", "course": "CS101"}
index.append(doc1)

doc2 = {"title": "Data Science", "description": "Python for data science", "course": "CS102"}
index.append(doc2)

# Search with custom stop words
index = AppendableIndex(
    text_fields=["title", "description"],
    keyword_fields=["course"],
    stop_words={"the", "a", "an"}  # Custom stop words
)
```
## Examples

### Interactive Notebook

The repository includes an interactive Jupyter notebook (`minsearch_example.ipynb`) that demonstrates the library's features using real-world data. The notebook shows:

- Loading and preparing documents from a JSON source
- Creating and configuring the search index
- Performing searches with filters and boosts
- Working with real course-related Q&A data

To run the notebook:

```bash
pipenv run jupyter notebook
```

Then open `minsearch_example.ipynb` in your browser.

## Development

### Running Tests

```bash
pipenv run pytest
```

### Building and Publishing

1. Install development dependencies:
```bash
pipenv install --dev twine build
```

2. Build the package:
```bash
pipenv run python -m build
```

3. Check the packages:
```bash
pipenv run twine check dist/*
```

4. Upload to test PyPI:
```bash
pipenv run twine upload --repository-url https://test.pypi.org/legacy/ dist/*
```

5. Upload to PyPI:
```bash
pipenv run twine upload dist/*
```

6. Clean up:
```bash
rm -r build/ dist/ minsearch.egg-info/
```

## Project Structure

- `minsearch/`: Main package directory
  - `minsearch.py`: Core Index implementation using scikit-learn
  - `append.py`: AppendableIndex implementation with inverted index
- `tests/`: Test suite
- `minsearch_example.ipynb`: Example notebook
- `setup.py`: Package configuration
- `Pipfile`: Development dependencies

Note: The `minsearch.py` file in the root directory is maintained for backward compatibility with the LLM Zoomcamp course.

---

## 📎 **Credits**  
> This content was adapted from the original [MinSearch repository](https://github.com/alexeygrigorev/minsearch) by [Alexey > Grigorev](https://github.com/alexeygrigorev). The structure and documentation have been included here for demo purposes within the > MinSearch RAG Pipeline project.
