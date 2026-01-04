# Agent-Based RAG Chatbot for Insurance Policy Analysis

This project develops a scalable and accurate Retrieval-Augmented Generation (RAG) system designed to process and analyze extensive insurance policy documents. By integrating advanced techniques like Adaptive & Corrective RAG, a web search agent, and a hallucination check, the system provides reliable and factually grounded answers to complex user queries.

-----

### Features

  * **Scalable Document Processing:** Efficiently ingests and processes large volumes of insurance policy documents (over 500 pages) from various PDFs.
  * **Adaptive & Corrective RAG:** Enhances retrieval accuracy by dynamically restructuring user queries and filtering out irrelevant document chunks, ensuring that only the most pertinent information is used for generation.
  * **Real-time Information Retrieval:** Integrates a **Web Search Agent** using Tavily Search to fetch up-to-date information that may not be present in the policy documents.
  * **Hallucination Prevention:** Incorporates a **Hallucination Check** mechanism that validates the generated response against the retrieved documents, significantly reducing misinformation.
  * **Structured Output:** Provides well-structured, comprehensive, and coherent answers based on a multi-step refinement process.

-----

### Core Architecture

The system operates on a sophisticated, multi-step RAG pipeline to generate high-quality responses:

1.  **Query Restructuring:** The initial user query is refined and broken down into multiple structured sub-queries to improve document retrieval.
2.  **Document Retrieval:** The system retrieves relevant documents from a vector store based on the restructured queries.
3.  **Document Refinement:** An LLM refines the retrieved documents by assigning relevance scores and filtering out irrelevant information.
4.  **Final Response Generation:** A comprehensive answer is generated using the refined, relevant document chunks.
5.  **Hallucination Check:** The final response is validated to ensure it is factually grounded and free of fabricated information.

-----

### Tech Stack

  * **Languages:** Python
  * **Frameworks:** LangChain, LangGraph, AutoGen, LlamaIndex, FastAPI
  * **Large Language Models (LLMs):** OpenAI (GPT-4o, text-embedding-3-small), LLaMA, GPT, Ollama
  * **Vector Databases:** ChromaDB, FAISS
  * **Utilities:** LlamaParse (for PDF to Markdown conversion), TavilySearchResults (for web search), Prompt Engineering, LoRA, QLoRA
  * **Environment:** Azure (for OpenAI services)

-----

### Setup and Installation

1.  **Clone the repository:**
    ```
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```
2.  **Create a virtual environment:**
    ```
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```
3.  **Install dependencies:**
    ```
    # Agentic AI based RAG chatbot — Document Analyzer

    A focused Retrieval-Augmented Generation (RAG) system to ingest, index, and analyze insurance policy documents and provide accurate, evidence-backed answers.

    Key goals:
    - Quickly ingest policies (PDF/Markdown) and create a searchable vector index
    - Use adaptive retrieval + refinement to surface the most relevant document excerpts
    - Validate responses against sources to reduce hallucination

    Highlights
    - Scalable document ingestion and chunking
    - Adaptive & corrective retrieval pipeline
    - Optional web search augmentation for up-to-date context
    - Hallucination check that cross-verifies answers against retrieved sources

    Quickstart
    1. Clone this repository and open the project root:

    ```powershell
    git clone https://github.com/ranit57/Agentic-AI-based-RAG-chatbot-Document-Analyzer.git
    cd "Agent-Based-RAG-Chatbot-for-Insurance-Policy-Analysis"
    ```

    2. Create and activate a virtual environment:

    ```powershell
    python -m venv venv
    venv\Scripts\activate
    pip install -r requirements.txt
    ```

    3. Add required secrets to a `.env` file (examples):

    ```
    AZURE_OPENAI_API_KEY=...
    AZURE_OPENAI_ENDPOINT=...
    OPENAI_API_KEY=...
    TAVILY_API_KEY=...
    ```

    4. Process policy PDFs to generate markdown and vectors (use `pdf_preprocessing.ipynb`):

    - Open `pdf_preprocessing.ipynb` and run the cells to convert PDFs in `data/input_data/pdf/` to markdown and to build the vector store.

    5. Run the interactive chatbot or API (project includes notebooks and a FastAPI scaffold).

    Usage example (Python)

    ```python
    from app.chat import generate_response

    resp = generate_response("Does HDFC ERGO Optima Secure cover AYUSH treatment?")
    print(resp)
    ```

    Where to look
    - Data input: `data/input_data/pdf/` and `data/input_data/markdown/`
    - Processing: `pdf_preprocessing.ipynb`
    - Main demos: `main.ipynb`

    Contributing
    - Update or add processing notebooks for new document types
    - Improve prompt templates and retrieval rules in the `app/` code

    License & Contact
    - This repository does not include a license file. Add `LICENSE` if you want to open-source it (MIT recommended).
    - Project owner: `ranit57` — ranitpal57@gmail.com

    If you'd like I can also tidy notebooks, add a `requirements.txt` if missing, or add a small `FastAPI` runner for demoing locally.
