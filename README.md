# Corrective RAG (CRAG)

A step-by-step implementation of **Corrective Retrieval-Augmented Generation**. Standard RAG trusts whatever the vector search returns. CRAG adds a check: it judges whether the retrieved documents are good enough to answer the question, and if they are not, it corrects course by refining the context and falling back to web search.

## The idea

```
question -> retrieve from vector DB -> evaluate retrieval quality
                                          |
              good enough ----------------+---> refine context -> generate answer
              not good enough / unsure ---+---> rewrite query -> web search -> generate answer
```

## Notebooks

Run them in order. Each one builds on the previous.

| Notebook | What it covers |
|---|---|
| `1_retrieval_refinement.ipynb` | Retrieving documents and refining the retrieved context before it reaches the model |
| `2_retrieval_evaluator.ipynb` | An evaluator that judges whether the retrieved documents are good enough |
| `3_web_search_refinement.ipynb` | Falling back to web search when the stored documents are not enough, and refining what comes back |
| `4_query_rewrite.ipynb` | Rewriting the user's question into a better query for search |
| `5_ambiguous.ipynb` | Handling the borderline case where the evaluator is not confident either way |

## Setup

Requires Python 3.9+.

```bash
git clone https://github.com/shubhamupadhyay12/Corrective-Rag.git
cd Corrective-Rag

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install notebook langchain langchain-community openai chromadb tavily-python
```

Set your API keys:

```bash
export OPENAI_API_KEY="your-openai-api-key"
export TAVILY_API_KEY="your-tavily-api-key"
```

Then start Jupyter and open the notebooks in order:

```bash
jupyter notebook
```

## Stack

Python, LangChain, ChromaDB (vector store), Tavily (web search), OpenAI, Jupyter

## License

MIT. See [LICENSE](LICENSE).

## Author

Shubham Upadhyay · [GitHub](https://github.com/shubhamupadhyay12) · [LinkedIn](https://www.linkedin.com/in/shubhamupadhyay25)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
