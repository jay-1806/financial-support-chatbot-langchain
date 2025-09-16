```markdown
# Financial Support Chatbot — LangChain + RetrievalQA

LLM-powered assistant for finance/billing questions. Combines document and database retrieval with prompt-engineered responses and source citations.

## Highlights
- **Retrieval:** Embedding index over invoice tables + policy/FAQ docs.
- **Reasoning:** LangChain chains (RAG) with reranking and guardrail fallbacks.
- **Integrations:** SQL connector for invoice lookups (payment status, totals, due dates).
- **UX:** Streamlit chat interface with cited sources and conversation history.

## Tech Stack
Python, LangChain, vector store (FAISS/Chroma), OpenAI/transformer LLMs, SQLAlchemy (Postgres/SQLite), Streamlit, Docker

## Architecture
1. Query → retrieval over vectorized docs + SQL semantic retrieval
2. Context assembly (top-k + rerank) → prompt template
3. LLM answer generation with citations and fallback policies
4. Optional redaction for PII, configurable through `.env`

## Project Structure
financial-support-chatbot-langchain/
├─ app/
│ └─ Home.py 
├─ data/
│ ├─ docs/ # policy/FAQ markdowns
│ └─ seeds/ # sample DB seeds
│ ├─ chains/
│ │ ├─ rag.py
│ │ └─ prompts.py
│ ├─ connectors/
│ │ └─ sql.py
│ ├─ guards/
│ │ └─ safety.py
│ └─ utils/
│ └─ logging.py
├─ requirements.txt
└─ README.md
