# CrocoIT RAG Chatbot

A RAG-powered chatbot that answers questions about CrocoIT
using content scraped from https://crocoit.com

## Approach
1. Scrape CrocoIT website using BeautifulSoup
2. Clean and chunk content using LangChain
3. Embed chunks using sentence-transformers (all-MiniLM-L6-v2)
4. Store vectors in FAISS vector store
5. Retrieve relevant chunks and answer using Google Gemini API

## Tools Used
- BeautifulSoup4 — web scraping
- LangChain — chunking and vector store
- Sentence Transformers — local embeddings
- FAISS — vector similarity search
- Google Gemini API — LLM for answer generation

## Project Structure
```
crocoit-rag-chatbot/
├── notebooks/
│   ├── 01_scraping.ipynb
│   ├── 02_chunking_embedding.ipynb
│   └── 03_rag_pipeline.ipynb
├── data/
│   └── raw_pages.json
├── vector_store/
├── .gitignore
└── README.md
```
## How to Run
1. Run 01_scraping.ipynb
2. Run 02_chunking_embedding.ipynb
3. Run 03_rag_pipeline.ipynb
4. Enter your Gemini API key when prompted

## Example Questions
- What services does CrocoIT offer?
- What is 2Loyal?
- What products does CrocoIT have?
- How can I contact CrocoIT?

## Challenges
- Website dynamic content required careful tag selection
- Duplicate chunks needed multiple cleaning passes
- Gemini API key secured via getpass (no .env needed)
- LangChain version conflicts resolved by pinning versions
