# Standard Course Q&A RAG System 📚🤖

An end-to-end Retrieval-Augmented Generation system that answers student questions using course materials and provides the sources used to generate each answer.

## Project Overview

This project builds a searchable knowledge base from multiple course files.

Instead of answering from the LLM's general knowledge, the system retrieves relevant information from the uploaded course materials and generates an answer based only on the retrieved context.

## Main Features

* Supports PDF, DOCX, TXT, and CSV files
* Extracts and cleans course content
* Splits documents into searchable chunks
* Generates embeddings locally using Ollama
* Stores embeddings in a FAISS vector database
* Filters results by course
* Answers questions using retrieved context only
* Displays source files with each answer
* Handles questions not covered by the course materials
* Provides an interactive Gradio interface

## RAG Pipeline

```text
Course Files
     ↓
Text Extraction
     ↓
Document Chunking
     ↓
Embedding Generation
     ↓
FAISS Vector Store
     ↓
Similarity Search
     ↓
Retrieved Context
     ↓
Llama 3.2
     ↓
Answer + Sources
```

## Technologies Used

* Python
* LangChain
* Ollama
* Llama 3.2
* Nomic Embed Text
* FAISS
* Gradio
* Jupyter Notebook

## Supported Course Materials

The knowledge base contains materials for three courses:

* Machine Learning
* Python
* Statistics

Supported file types:

```text
PDF | DOCX | TXT | CSV
```

## Project Structure

```text
Standard-Course-QA-RAG-System/
│
├── data/
│   ├── machine_learning/
│   ├── python/
│   └── statistics/
│
├── faiss_index/
├── screenshots/
├── Standard_RAG_Project.ipynb
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## Models

The project uses two local Ollama models:

```text
llama3.2:3b
nomic-embed-text
```

* `llama3.2:3b` generates the final answers.
* `nomic-embed-text` converts questions and document chunks into embeddings.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/essamawne7-wq/Standard-Course-QA-RAG-System.git
cd Standard-Course-QA-RAG-System
```

### 2. Create a virtual environment

```bash
py -3.13 -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install the requirements

```bash
pip install -r requirements.txt
```

### 4. Install Ollama

Download Ollama from:

https://ollama.com/download

### 5. Download the required models

```bash
ollama pull llama3.2:3b
ollama pull nomic-embed-text
```

### 6. Run the project

Open the Jupyter Notebook and run the cells in order.

## Example Question

```text
What is the difference between a list and a tuple?
```

Example answer:

```text
A list is an ordered and mutable collection, while a tuple is ordered but normally treated as immutable.
```

The system also displays the source:

```text
python_basics.docx
```

## Handling Unanswered Questions

If the retrieved course materials do not contain enough information, the system responds with:

```text
The answer was not found in the course materials.
```

This helps reduce hallucination and prevents the model from relying on unsupported general knowledge.

## What I Learned

Through this project, I gained practical experience with:

* Building an end-to-end RAG pipeline
* Processing multiple document formats
* Document chunking and metadata management
* Semantic search using embeddings
* Vector databases and similarity search
* Prompt engineering for grounded answers
* Source attribution
* Running LLMs locally with Ollama
* Building interactive AI applications with Gradio

## Future Improvements

* Add retrieval quality evaluation
* Rewrite weak user queries automatically
* Re-retrieve when the context is insufficient
* Add conversation history
* Support more document formats
* Develop the system into Corrective RAG
* Extend it later into Agentic RAG

## Author

**Essam Awne**

* GitHub: https://github.com/essamawne7-wq
* LinkedIn: Add your LinkedIn profile URL here

## License

This project is licensed under the MIT License.
