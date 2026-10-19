# ⚡ Chat with PDF - RAG Chatbot (Groq & BM25)

[![n8n workflow](https://img.shields.io/badge/n8n-Workflow-orange.svg)](https://n8n.io)
[![Sequence](https://img.shields.io/badge/Sequence-%2311-blue.svg)](#)
[![Difficulty](https://img.shields.io/badge/Difficulty-Advanced-green.svg)](#)
[![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen.svg)](#)

> **Workflow Sequence #11** in the [Maheen Azhar n8n Workflow Collection](https://github.com/maheenazhar/n8n-workflows-collection).

---

## 📖 Overview

Full Retrieval-Augmented Generation (RAG) system inside n8n: extracts text from PDF documents, performs BM25 keyword chunking & context retrieval, submits context-grounded queries to Groq LLM, and responds with cited answers.

### 🎯 Key Use Case
Interactive document question answering, policy document query chatbots, and technical documentation retrieval assistants.

---

## 🏗️ Architecture & Flow

```mermaid
graph TD
  N0_Webhook["Webhook<br><i>(webhook)</i>"]
  N1_Extract_PDF_Text["Extract PDF Text<br><i>(extractFromFile)</i>"]
  N2_Chunk___Retrieve__BM25_["Chunk & Retrieve (BM25)<br><i>(code)</i>"]
  N3_Groq_Chat_Completion["Groq Chat Completion<br><i>(httpRequest)</i>"]
  N4_Respond_to_Webhook["Respond to Webhook<br><i>(respondToWebhook)</i>"]
  N0_Webhook --> N1_Extract_PDF_Text
  N1_Extract_PDF_Text --> N2_Chunk___Retrieve__BM25_
  N2_Chunk___Retrieve__BM25_ --> N3_Groq_Chat_Completion
  N3_Groq_Chat_Completion --> N4_Respond_to_Webhook
```

---

## 🧩 Nodes in this Workflow

| # | Node Name | Type | Version |
|---|-----------|------|---------|
| 1 | **Webhook** | `n8n-nodes-base.webhook` | v2 |
| 2 | **Extract PDF Text** | `n8n-nodes-base.extractFromFile` | v1 |
| 3 | **Chunk & Retrieve (BM25)** | `n8n-nodes-base.code` | v2 |
| 4 | **Groq Chat Completion** | `n8n-nodes-base.httpRequest` | v4.2 |
| 5 | **Respond to Webhook** | `n8n-nodes-base.respondToWebhook` | v1.1 |

---

## 🔑 Prerequisites & Credentials

Before running this workflow, ensure you have the following configured in your n8n environment:

- [ ] **Groq API Key**
- [ ] **Binary file extract support in n8n**
- [ ] **Webhook endpoint tester**

> [!NOTE]
> All credentials are decoupled from this export file for security. When importing into your n8n workspace, re-assign your local credentials in the respective node configuration panels.

---

## 🚀 Setup & Installation

1. **Clone or Download:**
   ```bash
   git clone https://github.com/maheenazhar/n8n-11-chat-with-pdf-rag-chatbot.git
   cd n8n-11-chat-with-pdf-rag-chatbot
   ```
2. **Import into n8n:**
   - Open your n8n canvas.
   - Click the top-right menu `...` -> **Import from File**.
   - Select `workflow.json` from this repository.
   - *(Alternative)*: Open `workflow.json`, copy the entire JSON contents, and paste directly (`Ctrl+V`) onto the n8n canvas.
3. **Configure Credentials:**
   - Open each integration node marked with a red credential prompt.
   - Select or configure your accounts (e.g., Google OAuth, Groq API, Supabase, SMTP).
4. **Activate / Test:**
   - Click **Test step** or **Execute Workflow** to verify end-to-end functionality.
   - Toggle the workflow to **Active** for live production use.

---

## 📄 File Structure

```
11-chat-with-pdf-rag-chatbot/
├── workflow.json   # Full exportable n8n workflow definition
├── README.md       # Comprehensive documentation and architecture
└── .gitignore      # Standard Git exclusions
```

---

## 👤 Author & Repository

- **Author:** [Maheen Azhar](https://github.com/maheenazhar)
- **Workflow ID:** `6XwC234p5G4tJP9a`
- **Created Date:** `2026-10-09 13:29:45.118`
- **Last Modified:** `2026-10-09 15:24:19.767`
- **Repository:** [`https://github.com/maheenazhar/n8n-11-chat-with-pdf-rag-chatbot`](https://github.com/maheenazhar/n8n-11-chat-with-pdf-rag-chatbot)

---

*Part of the [n8n Workflows Collection](https://github.com/maheenazhar/n8n-workflows-collection) by Maheen Azhar.*
