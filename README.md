This is a RAG application that runs on local and uses Llama 3.1 8B model, nomic-embed-text, LangChain, Chromadb and pypdf for loading PDFs as text embeddings in Chromadb and then using them as context while querying Llama.

Steps to run RAG on local
1) Download Ollama https://ollama.com/download
2) Run Ollama
```
ollama serve
```
3) Pull Llama3.1 LLM and nomic-embed-text for text embeddings using below commands
```
ollama pull llama3.1
```
```
ollama pull nomic-embed-text
```
4) Install python dependencies
```
pip install -r requirements.txt
```
5) Add all the PDFs that needs to be indexed in the data directory of the project folder
6) Run below command to index them in Chromadb
```
python populate_database.py
```
7) Once indexing is done, we can now query the LLM. Since in this example we have indexed the PDF that has rules of the game monopoly we can ask it a question related to that.
```
python query_data.py "What are the rules for buying a house?"
```
