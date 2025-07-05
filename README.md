# 🧠 BIAssistant – AI-Powered Business Intelligence Chatbot

BIAssistant is an AI-powered assistant designed to help *non-technical users* explore and analyze business data intuitively — simply by asking questions in natural language.  
Whether you're a business analyst, a product manager, or an executive with no BI background, BIAssistant can help you understand your data warehouse and extract valuable insights.

---

## 🚀 Features

- 💬 *Conversational Interface* – Ask questions like:
  - "What are the top-performing products this month?"
  - "Which KPIs are underperforming this quarter?"
- 🧠 *Powered by Google Gemini* – Translates business questions into analytical strategies.
- 📚 *Schema-aware* – Understands fact tables, dimensions, and measures.
- 📊 *Works with Large Schemas* – Handles 150+ tables split across multiple JSON files.
- 🔍 *Vector-based Retrieval* – Uses FAISS to semantically match questions with relevant schema chunks.
- ⚙️ *Modular Design* – Can be integrated with internal tools, CRMs, or analytics dashboards.

---

## 🛠 Tech Stack

| Layer        | Technology        |
|--------------|-------------------|
| Frontend     | React + Vite      |
| Backend      | Flask             |
| AI Model     | Google Gemini     |
| Database     | Neo4j (Data Warehouse) |
| Vector Store | FAISS             |

---

## 🧱 How it Works

1. *Schema Extraction*  
   Neo4j is used to model your dimensional data warehouse (fact and dimension tables). A Python script extracts the schema, chunks it into JSON files, and saves it.

2. *Schema Summarization*  
   Each JSON file (representing a chunk of the schema) is summarized using a Gemini-powered prompt, creating a business-readable description.

3. *Vector Embedding*  
   The summarized schema chunks are embedded using FAISS for fast semantic retrieval.

4. *User Question Handling*  
   - User types a natural language question in the React UI.
   - The Flask backend receives it and uses FAISS to find the most relevant schema chunks.
   - It sends those chunks along with the user's question to Gemini with a BI-optimized prompt.
   - Gemini generates a structured response outlining:
     - Strategic objective
     - Key dimensions and measures
     - Analytical techniques
     - Actionable business insights

---
