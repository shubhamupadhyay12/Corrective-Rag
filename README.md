# Advanced RAG Pipeline & Query Processing Workflows

This repository contains a step-by-step modular implementation of advanced **Retrieval-Augmented Generation (RAG)** techniques. It covers concepts ranging from initial retrieval refinement and evaluation to integrating web search fallback, query rewriting, and handling ambiguous user queries.

---

## 📁 Repository Structure

```text
.
├── 1_retrieval_refinement.ipynb   # Advanced retrieval strategies & chunk refinement
├── 2_retrieval_evaluator.ipynb    # Evaluation metrics for retrieved context & answers
├── 3_web_search_refinement.ipynb  # Integrating fallback web search into RAG pipelines
├── 4_query_rewrite.ipynb          # Transforming & optimizing queries for vector search
└── 5_ambiguous.ipynb              # Handling ambiguous user intent & disambiguation workflows
```

---

## 🚀 Workflows & Notebook Breakdown

### 1. Retrieval Refinement (`1_retrieval_refinement.ipynb`)
Focuses on enhancing the quality of document retrieval before passing chunks to the LLM. Includes context filtering, re-ranking, and dynamic chunk selection to reduce noise.

### 2. Retrieval Evaluator (`2_retrieval_evaluator.ipynb`)
Evaluates the performance of the retrieval and generation components using quantitative metrics (e.g., faithfulness, context precision, recall, and answer relevance).

### 3. Web Search Integration (`3_web_search_refinement.ipynb`)
Combines local vector databases with real-time web search APIs to handle out-of-domain queries or dynamic real-time information missing from static knowledge bases.

### 4. Query Rewriting (`4_query_rewrite.ipynb`)
Implements query expansion, sub-query decomposition, and hypothetical document embeddings (HyDE) to reformulate raw user prompts into optimal search queries.

### 5. Ambiguous Query Handling (`5_ambiguous.ipynb`)
Detects underspecified or ambiguous queries and executes interactive workflows (such as asking clarifying questions or branching search paths) to ensure precise answers.

---

## 🛠️ Prerequisites & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/shubhamupadhyay12/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Install Dependencies
Make sure you have Python 3.9+ installed. You can set up a virtual environment and install the required packages:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install notebook langchain langchain-community openai chromadb ragas tavily-python
```

*(Note: Adjust package installations based on the specific framework/LLM providers used in your notebooks, e.g., OpenAI, Ollama, LangChain, LlamaIndex).*

### 3. Set Up API Keys
Set your environment variables for your LLM and Web Search providers:

```bash
export OPENAI_API_KEY="your-openai-api-key"
export TAVILY_API_KEY="your-tavily-api-key"
```

---

## 💻 Usage

Run the Jupyter Notebook server:

```bash
jupyter notebook
```

Execute the notebooks sequentially from `1_retrieval_refinement.ipynb` to `5_ambiguous.ipynb` to follow the full pipeline progression.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
