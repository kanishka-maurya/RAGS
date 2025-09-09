# 🤔 What is RAG?  

**Retrieval-Augmented Generation (RAG)** is an approach that combines two powerful steps:  

1. **Retrieval** – Relevant information is first fetched from an external knowledge source (e.g., a vector database, document collection, or knowledge base).  
2. **Generation** – The retrieved information is then passed to a Large Language Model (LLM), which uses it to generate a more accurate and context-aware response.  

### Why use RAG?  
- **Without RAG**: The LLM answers only from its internal training data, which may be outdated or incomplete.  
- **With RAG**: The LLM grounds its responses on the most relevant and up-to-date documents, leading to **factual, reliable, and explainable outputs**.  

In short, RAG bridges the gap between **stored knowledge** and **language generation**, making AI systems significantly more robust and trustworthy. 🚀  


# 📘 RAG with LangChain  

This notebook shows how to build a **Retrieval Augmented Generation (RAG) pipeline** using LangChain, Groq, and Nomic embeddings.  

---

## 🚀 Steps Covered  

1. **Environment Setup**  
   - Load API keys (`LangSmith`, `Groq`, `Nomic`) via `.env`  
   - Enable **LangSmith tracing** for monitoring  

2. **Web Scraping & Loading**  
   - Use `WebBaseLoader` + BeautifulSoup (`SoupStrainer`)  
   - Extract only useful parts of a webpage (`post-content`, `post-title`, `post-header`)  

3. **Splitting Documents**  
   - Split long text into chunks with `RecursiveCharacterTextSplitter`  
   - Config: `chunk_size=1000`, `chunk_overlap=200`  

4. **Embeddings & Vector DB**  
   - Generate embeddings with **Nomic Embeddings**  
   - Store chunks in **ChromaDB**  
   - Convert into a retriever  

5. **LLM + Prompt**  
   - Load a **RAG prompt template** from LangChain Hub  
   - Use **Groq Llama3** model to generate grounded answers  

6. **RAG Chain**  
   - Retrieve docs → format as context → send with question → parse answer  
   - Example query: *“What is task decomposition?”*  

---

## 📌 Key Learnings  

- **RAG = Retrieval + Generation** → first fetch relevant info, then answer with LLM  
- **Chunks** are based on characters (not words)  
- Web scraping depends on HTML structure (`class_` in BeautifulSoup)  
- **LangSmith** helps trace, debug, and monitor your pipeline  

---

✅ In essence: The notebook demonstrates **end-to-end RAG** → scrape website → split text → embed → store → retrieve → answer with LLM.  
