# Full RAG Pipeline

A simple **Retrieval-Augmented Generation (RAG)** system built from scratch using **MiniLM** and **DistilBERT**. This project demonstrates how to combine a **retriever** and a **generator** to build a fact-based question-answering pipeline.

---

## 🚀 Overview

RAG systems enhance AI by retrieving **relevant information** before generating answers, helping prevent hallucinations and ensuring more accurate responses.

This project consists of:

1. **Retriever (MiniLM)** 🔎  
   - Converts queries into embeddings.  
   - Performs **semantic search** on a knowledge base to find the most relevant context.  

2. **Generator (DistilBERT)** ✍️  
   - Takes the retrieved context and extracts the exact answer.  
   - Ensures answers are factually grounded.

---

## 📚 Knowledge Base

The system uses a simple knowledge base of documents as the "long-term memory":

```python
knowledge_base = [
    "Buddy is a 3-year-old Golden Retriever who loves to play fetch.",
    "The capital of France is Paris, which is known for the Eiffel Tower.",
    "Python is an interpreted, high-level, general-purpose programming language.",
    "The first person to walk on the Moon was Neil Armstrong in 1969.",
    "Climate change is the long-term alteration of temperature and typical weather patterns."
]
````

---

## 🧠 How It Works

1. **Encoding Knowledge**
   The Retriever converts all documents in the knowledge base into embeddings using MiniLM.

2. **Retrieval Step**
   A user's query is encoded and compared with the knowledge base embeddings.
   The most relevant document is selected using **cosine similarity**.

3. **Generation Step**
   The selected context and the user's question are passed to DistilBERT, which extracts the precise answer.

4. **End-to-End Pipeline**
   The `ask_rag_pipeline(query)` function connects the retriever and generator to provide the final answer.

---

## ⚙️ Tech Stack

* Python
* [sentence-transformers](https://www.sbert.net/) (MiniLM)
* [transformers](https://huggingface.co/transformers/) (DistilBERT QA pipeline)
* PyTorch

---

## 💡 Example Usage

```python
from mini_rag import ask_rag_pipeline

query = "What is the capital of France?"
answer, context = ask_rag_pipeline(query)

print("Query:", query)
print("Retrieved Context:", context)
print("Answer:", answer)
```

**Output:**

```
Query: What is the capital of France?
Retrieved Context: The capital of France is Paris, which is known for the Eiffel Tower.
Answer: Paris
```

---

## 🔗 GitHub

[Linkedin](www.linkedin.com/in/ayah-alhassany)


