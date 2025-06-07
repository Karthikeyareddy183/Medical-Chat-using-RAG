# 🧠 AI Medical Assistant Bot (n8n + LangChain + Pinecone)

This project is an **AI-powered Medical Q&A Assistant** built using [n8n](https://n8n.io), [LangChain](https://www.langchain.com/), [Pinecone](https://www.pinecone.io/), and [OpenRouter](https://openrouter.ai/). It is designed to **answer questions from specific medical textbooks** such as *CLINICAL EXAMINATION BOOK* and *Diseases of ENT*.

---

## 📌 Features

- ✅ Accepts messages via chat trigger (n8n chatbot).
- ✅ AI Agent powered by OpenRouter LLM (via OpenRouter API).
- ✅ RAG (Retrieval-Augmented Generation) using Pinecone + Hugging Face Embeddings.
- ✅ Knowledge-limited: Answers **only from PDF documents** in the vector store (no hallucination).
- ✅ Stores short-term memory using LangChain's `MemoryBufferWindow`.
- ✅ Responds in patient-friendly, non-technical language.

---

## 🧱 Architecture

```text
[ChatTrigger] --> [AI Agent]
                  |--> OpenRouter (LLM)
                  |--> Pinecone Vector Store (Search)
                        |--> HuggingFace Embeddings
                  |--> Simple Memory (LangChain)
