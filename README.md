# Al-powerd-chatbot
Descriptions:
 **AI-Powered Chatbot – Description**
This chatbot is a **hybrid FAQ and conversational assistant** built using **Natural Language Processing (NLP)**. It combines **retrieval-based** and **generative-based** approaches to provide contextual, intelligent responses for **customer support or FAQ automation**.

**Core Features**
1. **Retrieval-based Answers**

   * Uses a **semantic search model** (`sentence-transformers/all-MiniLM-L6-v2`) to match user queries with stored FAQ entries in an SQLite database.
   * Returns the most relevant pre-written answer if the similarity score is above a threshold.

2. **Generative Fallback**

   * If no good FAQ match is found, it switches to a **Transformer-based chatbot model** (`microsoft/DialoGPT-small`) to generate responses dynamically.
   * Incorporates **recent conversation history** for more natural, context-aware replies.

3. **Database Integration**

   * Stores FAQs and chat logs in **SQLite**.
   * Allows adding new FAQs via an **admin endpoint**.
   * Maintains conversation history for each `conversation_id`.

4. **API-based Architecture**

   * Built with **FastAPI** for quick and scalable deployment.
   * Provides REST endpoints for:

     * Chat interaction (`/chat`)
     * Adding FAQs (`/admin/add_faq`)
     * Viewing FAQs and logs

5. **Text Preprocessing**

   * Uses **NLTK** for sentence tokenization.
   * Ensures clean and consistent text input before embedding or generation.

### **Technology Stack**

* **Language:** Python
* **Framework:** FastAPI
* **NLP Libraries:**

  * **Sentence Transformers** (semantic search)
  * **Transformers** (DialoGPT model for generation)
  * **NLTK** (tokenization)
* **Database:** SQLite
* **Environment:** Works on CPU or GPU (Torch backend)

---

### **How It Works**

1. **User sends a query** (via API).
2. **Preprocessing**: Text is tokenized and cleaned.
3. **Semantic Search**: Query is embedded and compared against FAQ embeddings.
4. If **high-confidence match found** → Return stored FAQ answer.
5. If **no match** → Use **generative model** to create a response.
6. **Log everything** (user and bot messages) in the database.

### **Outcome**

* A **deployable chatbot service** that:

  * Handles repetitive FAQ queries instantly.
  * Falls back to conversational AI for non-FAQ questions.
  * Keeps a history of interactions for analytics or improvements.
* Suitable for **customer service**, **website support**, or **internal helpdesk bots**.


Output:
<img width="1024" height="1024" alt="Image" src="https://github.com/user-attachments/assets/4baa8ae3-c578-40d5-8cc3-1dc1759559e3" />
