### RAG Assistant System
This project implements a chatbot system that leverages the RAG (Retrieval-Augmented Generation) architecture using the LangChain framework in Python. The primary objective is to create an assistant capable of providing accurate, contextually relevant, and up-to-date answers by retrieving information from an external knowledge base before generating a response.

### What is Retrieval-Augmented Generation (RAG)?
RAG is a powerful technique that enhances the capabilities of Large Language Models (LLMs) by mitigating common issues like hallucination and out-of-date knowledge. The process involves a multi-stage pipeline:

- Ingestion & Indexing: Raw documents from a knowledge base (e.g., PDFs, text files) are processed. This typically involves splitting the documents into smaller, semantically meaningful chunks. These chunks are then converted into numerical representations, known as embeddings, using an embedding model. The embeddings are stored in a vector database (e.g., FAISS) for efficient semantic search.

- Retrieval: When a user submits a query, the system converts the query into an embedding. This query embedding is then used to perform a similarity search within the vector database. The goal is to retrieve the most relevant document chunks (the "context") that are semantically similar to the user's question.

- Augmentation & Generation: The retrieved context, along with the user's original query, is fed into a Large Language Model (LLM). The LLM is then prompted to synthesize this information and formulate a coherent and informed response. This process ensures the LLM's output is grounded in the provided external data rather than relying solely on its pre-trained knowledge.

This architecture enables the chatbot to maintain a dynamic and verifiable knowledge base, providing a more reliable and extensible solution for a wide range of applications.

### Technologies Used
- Python: The core programming language for the project.

- LangChain: The orchestrator framework for building and chaining the RAG pipeline components.

- OpenAI: Utilized for the LLM and embedding models. An API key is required.

- FAISS: A library for efficient similarity search and clustering of dense vectors, used as the vector store.

- Other Libraries: tiktoken, langchain-openai, fastapi, uvicorn, etc., for tokenization, API integration, and serving the application.

### Prerequisites
Before starting, ensure you have the following installed:

- Python 3.10 or higher

- pip (Python's package installer)

### Installation and Setup
Follow these steps to set up the project on your local machine.

Clone the repository:
```
git clone https://github.com/thiagoribeiro00/assistant-rag-sistem.git
cd assistant-rag-sistem
```

Create and activate a virtual environment:
```
python3 -m venv venv
source venv/bin/activate  # On Linux/macOS
# or
# venv\Scripts\activate.bat  # On Windows
```

Install project dependencies:
```
pip install -r requirements.txt
```
Configure your OpenAI API key:
Create a file named .env in the project root directory and add your key:

```
OPENAI_API_KEY="your_api_key_here"
```

### Add documents to the knowledge base:
Place the documents (e.g., PDF, TXT) that you want the chatbot to reference in the designated directory, as defined by the project's code.

### How to Run
To start the chatbot, the instructions may vary depending on the specific implementation (command-line or web server).
:

```
docker-compose up --build
```