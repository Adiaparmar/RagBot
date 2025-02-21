# RAGBot: Retrieval-Augmented Chatbot with Ollama and LangChain

RAGBot is a retrieval-augmented generation (RAG) chatbot built with Ollama and LangChain. It combines document retrieval with natural language generation to answer questions based on provided context. This project uses `llama3` for text generation and `nomic-embed-text` for embeddings, all running locally via Ollama in a Jupyter notebook.

## Features
- **Retrieval-Augmented Generation**: Answers questions by retrieving relevant document snippets and generating responses.
- **Local LLM**: Powered by Ollama, running `llama3` and `nomic-embed-text` on your machine.
- **Customizable**: Easily swap models or add your own documents in the notebook.

## Prerequisites
- **Python**: Version 3.11 or 3.13 (tested with 3.13).
- **Ollama**: Local inference server for LLMs.
- **Git**: For cloning this repository.
- **Jupyter**: To run the notebook.

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ragbot.git
cd ragbot
```
### 2. Install Ollama
-Download and install Ollama from ollama.ai.
-Pull the required models:

```bash
ollama pull llama3
ollama pull nomic-embed-text
```
-Start the Ollama server:

```bash
ollama serve
```
-Keep this running in a separate terminal.

### 3. Set Up Python Environment
Create a virtual environment:

```bash
python -m venv .venv
```

Activate it (Windows):

```bash
.venv\Scripts\activate.bat
```

(Linux/macOS: source .venv/bin/activate)

Install dependencies:

```bash
pip install -r requirements.txt
```
### 4. (Optional) Configure API Keys
If using Gemini models, create a .env file based on .env.example:

```bash
GOOGLE_API_KEY=your-api-key-here
```
### 5. Run the Notebook
-Launch Jupyter:

```bash
jupyter notebook
Open ragbot.ipynb and run all cells.
```

## Usage
The notebook demonstrates asking "What is Docker?" using a small sample dataset.

Modify the pages list in the notebook to use your own documents.

Run the chain to ask any question based on your data:

```python
response = chain.invoke({"question": "Your question here"})
print(response)
```

## Project Structure
- ragbot.ipynb: Main notebook with the RAG chatbot implementation.
- requirements.txt: Python dependencies.
- .env.example: Template for environment variables.
- .gitignore: Excludes virtual env and temp files.
- README.md: You’re reading it!
  
## Dependencies
- See requirements.txt for the full list. Key packages:
  
langchain-ollama
langchain-community
langchain-core
docarray

## Notes
- **Performance**: Runs on CPU by default. Expect 20-60s per response without a GPU. For faster results, use a GPU-enabled system with Ollama’s CUDA support.
- **Memory**: Requires at least 4 GiB free RAM (8 GiB recommended).

## Contributing
Feel free to fork, submit PRs, or open issues for improvements!

## License
MIT License—see LICENSE if you add one.
