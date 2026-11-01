# RAG Engineering

Course materials for **RAG Engineering — From Retrieval to Production**. The repo currently contains Lecture 1, an interactive Jupyter notebook that teaches the foundations of Retrieval-Augmented Generation.

## What's inside

| File | Purpose |
|---|---|
| `RAG_Foundations.ipynb` | Lecture 1 — RAG Foundations, an interactive demo with widgets |
| `.env.example` | Template for the API configuration |
| `pyproject.toml` / `uv.lock` | Dependencies, managed with [uv](https://docs.astral.sh/uv/) |
| `main.py` | Placeholder entry point |

## Lecture 1 topics

- How LLMs work: next-token prediction, a bigram model, and a tiny neural net where you can see knowledge stored in the weights
- Transformer building blocks: byte pair encoding, positional encoding, multi-head self-attention, feed-forward networks and gradient descent
- Why attention cost grows quadratically with prompt length
- LLM limitations (hallucination, stale knowledge, no sources) and how to diagnose them
- The four layers of freshness, and the grounding rule for prompts
- A from-scratch TF-IDF retriever that shows the whole RAG idea with no framework or vector database
- When to use RAG versus long context, plus a decision wizard and architecture overview
- A demo knowledge base of twelve documents with department, version, status and access-level metadata

## Requirements

- Python 3.13 or newer
- [uv](https://docs.astral.sh/uv/)
- An API key for the EURI gateway (OpenAI-compatible). This is optional. Without a key, the notebook warns you at the top and falls back to a local stand-in.

## Setup

```bash
uv sync
cp .env.example .env
```

Edit `.env`:

```bash
EURI_API_KEY=your-key-here
EURI_CHAT_MODEL=gpt-4.1-mini
EURI_EMBEDDING_MODEL=<embedding model enabled on your account>
EURI_EMBEDDING_DIMENSION=1536
```

The notebook loads `.env` automatically with `python-dotenv`. `.env` is git-ignored, so keep your key there.

## Running the notebook

1. Open `RAG_Foundations.ipynb` in VS Code or Jupyter.
2. Select the `.venv` kernel created by `uv sync`.
3. Run `Kernel → Restart & Run All` once, then present from the top.

Cells marked 🎤 are speaker tips.
