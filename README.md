# RAG from Scratch

My own take on learning **RAG — Retrieval-Augmented Generation** — by rebuilding it from the ground up.

This is a series I started for myself, to actually *understand* RAG instead of just wiring libraries together. It's heavily motivated by the excellent YouTube series [_RAG From Scratch_](https://youtu.be/sVcwVQRHIc8?si=oOds6Njaj0WTOvq3), which I recently finished. The topics and explanations there were so well chosen that I decided to **rewrite every example myself** — with:

- my own understanding
- my own words
- my own examples

Each notebook is written rough first, then polished — so the explanations read like notes from someone learning, not documentation.

## Why RAG (the short version)

- An LLM is like a super-intelligent person who has read all the books and the whole internet — but all of that knowledge is **public**.
- It can't help you with information that only *you* have.
- **RAG** bridges that gap: retrieve the relevant private/external context first, then let the LLM generate an answer grounded in it.

## Getting started

```bash
# clone
git clone <your-repo-url>
cd rag-from-scratch

# install dependencies (uv reads pyproject.toml + uv.lock)
uv sync
```

Then create a `.env` file in the project root with your API keys:

```env
GROQ_API_KEY=your_groq_key
OPENROUTER_API_KEY=your_openrouter_key
TAVILY_API_KEY=your_tavily_key
```

Launch the notebooks with your editor of choice (VS Code, JupyterLab, etc.) and run the cells top to bottom.

## Credits

Inspired by the [_RAG From Scratch_](https://youtu.be/sVcwVQRHIc8?si=oOds6Njaj0WTOvq3) series. The code here is my own re-implementation — written to learn, in my own voice.