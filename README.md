#  📘 RAG on Legal Documents

## 🧾 Overview

This project focuses on processing and analyzing a collection of legal agreements (e.g., NDAs, contracts, privacy policies) to build a **`Retrieval-Augmented Generation (RAG)** system for tasks such as information retrieval, question-answering, and knowledge extraction.

The system leverages **LangChain**, **OpenAI embeddings**, and **ChromaDB** to process legal documents and evaluate performance using metrics like **ROUGE**, **BLEU**, and **RAGAS**.

The zip file (**`RAG_Legal_Docs_ArnabBiswas_BhimSingh_MaddiPranavReddy.zip`**) contains the .ipynb file (`RAG_Assg_Legal_Documents_ArnabBiswas_BhimSingh_MaddiPranavReddy.ipynb`) has complete workflow including:

- Data loading
- Preprocessing
- Exploratory Data Analysis (EDA)
- RAG pipeline setup
- Evaluation
- Insights

---

## 🎯 Objectives

- **Understand the Dataset:** Analyze the structure, content, and context of the legal document dataset.
- **Perform Exploratory Analysis:** Conduct bivariate and multivariate analyses.
- **Create Visualizations:** Support findings with visual summaries.
- **Derive Insights:** Extract and summarize key learnings.
- **Document the Process:** Ensure reproducibility and clarity.
- **Build a RAG System:** Enable advanced legal document processing.

---

## 💼 Business Value

The RAG system enhances legal document processing for:

- ⚖️ **Faster Legal Research**
- 📄 **Improved Contract Analysis**
- 📊 **Regulatory Compliance Monitoring**
- 🧠 **Enhanced Decision-Making**

### 🔧 Use Cases
- Legal chatbots
- Contract review automation
- Compliance monitoring
- Case law analysis
- Risk assessment

---

## 👨‍💻 Team Members

- **Arnab Biswas**  
- **Bhim Singh**  
- **Maddi Pranav Reddy**

---

### 📊 Dataset Statistics
- **Total Documents:** 698  
- **Avg Length:** 16,188 words  
- **Min Length:** 228 words  
- **Max Length:** 157,239 words  

## 🧪 Methodology

### 1. Data Loading & Preprocessing
- Loaded `.txt` files via `os.walk`
- Cleaned special characters, URLs, emails, phone numbers
- Lemmatized and normalized text
- Skipped corrupted files with logs

### 2. Exploratory Data Analysis (EDA)
- Document length stats
- TF-IDF and word frequencies
- Cosine similarity analysis
- Word clouds and visual summaries

### 3. RAG Pipeline Setup
- **LangChain**-based architecture
- **Text Splitter:** RecursiveCharacterTextSplitter (chunk_size=512, overlap=50)
- **Embeddings:** OpenAI `text-embedding-3-small`
- **Vector Store:** ChromaDB
- **LLM:** gpt-4o-mini
- **Prompt:** Customized for legal QA

### 4. Evaluation Metrics
| Metric              | Score  | Interpretation                          |
|---------------------|--------|------------------------------------------|
| ROUGE-1             | 0.305  | Moderate unigram overlap                |
| ROUGE-2             | 0.111  | Poor bigram overlap                     |
| ROUGE-L             | 0.217  | Moderate LCS overlap                    |
| BLEU                | 0.057  | Low precision similarity                |
| Answer Relevancy    | 0.671  | Moderate question alignment             |
| Context Precision   | 0.722  | High-quality context                    |
| Faithfulness        | 0.717  | Accurate answer-context relation        |
| Context Recall      | 0.672  | Moderate context coverage               |
| **Overall QA Score**| **0.434** | Moderate performance                   |

### 5. Insights and Conclusions
- Effective text normalization
- Strong context precision and faithfulness
- Challenges in exact text match due to legal language

---

📌 Sample Outputs


Q1: Does the NDA grant the Receiving Party rights to Confidential Information?
→ Answer: "No, the Agreement does not grant rights..."

Q2: Is Confidential Information limited to technical info?
→ Answer: "Not found in provided context."

Q3: Do obligations survive termination?
→ Answer: "Yes, obligations of confidentiality survive."
