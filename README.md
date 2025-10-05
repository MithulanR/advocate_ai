⚖️ Advocate AI: Legal Research Assistant
Advocate AI is a powerful legal research tool built with Streamlit and leveraging advanced Retrieval-Augmented Generation (RAG) techniques. It provides highly structured, evidence-based answers to complex legal questions by combining large language models (via OpenRouter) with a proprietary knowledge base (FAISS) and user-uploaded PDF documents.

✨ Key Features
Hybrid Search RAG: Uses a combination of Semantic Search (Sentence Transformers + FAISS) and Lexical Search (BM25) with Reciprocal Rank Fusion (RRF) for highly relevant context retrieval.

Structured Legal Answers: Enforces a rigid, didactic output structure (Short Answer, Doctrine, Distinction, Summary Table, Conclusion) for clear legal analysis.

LLM Prompt Refinement: Uses an LLM to refine ambiguous user questions into clearer prompts, ensuring better search and generation results.

PDF Integration: Users can upload PDFs to include their specific case law or documents in the RAG context.

Conversation Tools: Includes keyword highlighting, text-to-speech audio output, and PDF export of the entire Q&A session.

Modular Architecture: Models and indexing are cached using @st.cache_resource for efficient performance.

🚀 Installation and Setup
1. Clone the Repository
Bash

git clone https://github.com/your-username/advocate-ai.git
cd advocate-ai
2. Set Up the Environment
It is highly recommended to use a virtual environment.

Bash

# Create and activate environment
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
3. Install Dependencies
Install all required Python packages:

Bash

pip install -r requirements.txt
4. NLTK Data
The application automatically downloads necessary NLTK data (stopwords, punkt) if missing, but you can pre-download them:

Python

import nltk
nltk.download('stopwords')
nltk.download('punkt')
🔑 API Key Configuration
This application uses the OpenRouter platform to access various large language models (LLMs).

Create an account and get an API key from OpenRouter.

Create a secret configuration directory and file:

Bash

mkdir -p .streamlit
touch .streamlit/secrets.toml
Add your API key to the secrets.toml file:

Ini, TOML

# .streamlit/secrets.toml
OPENROUTER_API_KEY="sk-or-v1-YOUR-ACTUAL-KEY-GOES-HERE"
🧱 Knowledge Base Files (RAG)
The application relies on two local files for its knowledge base:

faiss_advanced_index.bin

metadata.pkl

You must place these two files in the project root directory. If they are missing, the application will display an error and stop. These files are typically created via a separate script (an embedding pipeline) that processes your corpus of legal documents.

▶️ How to Run
Start the Streamlit application from your terminal:

Bash

streamlit run app.py
The app will open automatically in your browser (usually at http://localhost:8501).

📚 Usage Guide
Select a Model: Choose your preferred LLM from the sidebar (e.g., google/gemini-2.5-flash).

Upload Documents (Optional): Use the "Upload PDFs" uploader to include documents specific to your research.

Enter Your Question: Type your legal research question in the chat input and press Enter.

Refine Prompt: The app will present 2-3 refined versions of your question. Select the best one to proceed.

View Answer: The LLM will provide a structured answer, complete with a legal breakdown, distinction analysis, and a summary table.

Use Tools:

Keyword Highlight: Enter terms in the sidebar to bold them in the answer.

Audio Output: Listen to the generated answer using the embedded audio player.

Download PDF: Export the entire Q&A conversation history and PDF summaries into a clean, official PDF report.

🤝 Contributing
Contributions are welcome! If you have suggestions for new features, better RAG techniques, or bug fixes, please open an issue or submit a pull request.



✉️ Contact
Developer: Mithulan R

Email: mithulanr2003@gmail.com
