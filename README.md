# fidelity-ai-financial-advisor-rag
For your GitHub repository, you need a **README** that doesn't just show your code, but also shows your **engineering mindset**. Since you are applying for a Senior role, LinkedIn wants to see that you can evaluate different tools and pick the best one for the business.

Here is the complete, professional content for your `README.md`. It uses simple, direct English and incorporates all 8 of your experiments into a powerful comparison table.

---

# Fidelity AI Financial Advisor: A Comparative RAG Benchmark

This project is a production-grade AI Agent designed to act as a **Fidelity Financial Advisor**. It specialized in answering complex questions about retirement planning and mutual funds by retrieving data from official Fidelity documentation and web sources.

### 🎯 The Problem

In the financial sector, AI "hallucinations" are a major risk. A financial advisor agent must be 100% accurate, cite its sources, and know when to say "I don't know." I built this system to evaluate which combination of LLMs and frameworks (LangChain vs. LlamaIndex) provides the most reliable and cost-effective advice.

---

### 📊 8-Experiment Comparative Analysis

I conducted 8 distinct experiments to baseline performance across different models (OpenAI, Llama 3, DeepSeek) and orchestration frameworks.

| Exp # | Platform | Model | Framework | Key Verdict |
| --- | --- | --- | --- | --- |
| **01** | Ollama | Llama 3.2 (3B) | LangChain | **Best for Privacy:** Secure, local-only execution. |
| **02** | Replicate | Llama 3 (70B) | LangChain | **Best Reasoning:** Excellent semantic depth. |
| **03** | **OpenAI** | **GPT-4o-mini** | **LangChain** | **WINNER:** Highest correctness and lowest latency. |
| **04** | Ollama | Llama 3.2 (3B) | LlamaIndex | Solid indexing, but lower conversational fluency. |
| **05** | Replicate | Llama 3 (70B) | LlamaIndex | Strong for document-heavy PDF analysis. |
| **06** | OpenAI | GPT-4o-mini | LlamaIndex | Very efficient and structured for metadata. |
| **07** | Replicate | DeepSeek-R1 | LangChain | Emerging low-cost alternative to Llama-3-70B. |
| **08** | Replicate | DeepSeek-R1 | LlamaIndex | Best cost-performance for enterprise docs. |

---

### 🧠 Key Engineering Insights

#### **1. Why LangChain/LangGraph?**

My experiments (Exp 1, 2, 3, 7) showed that **LangGraph** provided superior "control flow." I implemented a **binary relevance check**: the agent first verifies if a document is relevant to the user's retirement query before it is allowed to generate an answer. This "loop" logic significantly reduced hallucinations.

#### **2. Performance vs. Cost**

While **DeepSeek-R1 (Exp 8)** performed surprisingly well for a low-cost model, **GPT-4o-mini (Exp 3)** was the most "production-ready." It balanced speed with high-quality formatting for step-by-step retirement savings strategies.

#### **3. Privacy and Scalability**

For clients requiring strict data privacy, **Experiment 1 (Ollama)** proved that we can run a responsive financial advisor entirely offline on local hardware without any external API calls.

---

### 🛠️ Technical Stack

* **Frameworks:** LangChain v0.3, LangGraph, LlamaIndex.
* **Vector Store:** ChromaDB (for persistent document indexing).
* **Models:** GPT-4o-mini, Meta Llama 3.2, DeepSeek-R1.
* **Tools:** PyMuPDF (PDF extraction), WebBaseLoader (Real-time web scraping).

### 🚀 Getting Started

1. **Clone the repo:** `git clone https://github.com/your-username/fidelity-rag-advisor`
2. **Install requirements:** `pip install -r requirements.txt`
3. **Environment Variables:** Create a `.env` file and add your `OPENAI_API_KEY` or `REPLICATE_API_TOKEN`.
4. **Run:** Open `notebooks/03_openai_langchain_gpt4o_mini.ipynb` to see the recommended architecture.

### 🛡️ Security Note

All API keys used during the development of these 8 experiments have been **revoked**. The code now uses environment variables to ensure security best practices.
 