# 🚫💸 FRAUD ZERO 

**An AI-Powered Expense Report Generator with Fraud Detection**  
*Built by Team py.charmers*

---

## 📖 Project Overview

**Fraud Zero** is an intelligent, automated platform designed to streamline the generation of corporate expense reports while rigorously enforcing fraud detection and policy compliance. By leveraging state-of-the-art AI, Optical Character Recognition (OCR), and machine learning, this platform significantly reduces manual effort, prevents financial leaks, and provides actionable insights for enterprise financial optimization. 

Our system not only extracts data from invoices and receipts with high accuracy but also acts as an active compliance guard. Through advanced anomaly detection models and a dynamic policy chatbot, Fraud Zero ensures that every penny claimed aligns with company guidelines.

## 🎯 Why Do We Need Fraud Zero?

Traditional expense reporting is tedious, error-prone, and highly susceptible to fraudulent claims. Fraud Zero tackles these industry-wide challenges by:
*   **Eliminating Manual Errors & Reducing Processing Time:** Automating data entry straight from receipts.
*   **Preventing Expense Fraud & Detecting Anomalies:** Catching duplicate claims, unusual spending patterns, and inflated costs in real-time.
*   **Enhancing Compliance & Policy Adherence:** Empowering employees to understand policies via an AI chatbot before submitting expenses.
*   **Securing Sensitive Financial Data:** Ensuring that managers and employees only see what they are authorized to see.
*   **Providing Actionable Insights:** Generating comprehensive reports that help companies optimize their travel and operational budgets.

## ✨ Key Features
<img width="1354" height="686" alt="Picture7" src="https://github.com/user-attachments/assets/cc82304e-0223-47ac-9bba-ed515cf8e0ca" />

*   🤖 **Automated Expense Processing:** Eliminates manual data entry by extracting text directly from receipts and invoices using **PaddleOCRx**.
*   🕵️ **Advanced Fraud Detection:** Utilizes **AutoEncoders** and vector-based clustering to detect anomalies, flag suspicious transactions, and identify duplicate claims.
*   💬 **Intelligent Policy Assistant (RAG Chatbot):** A Retrieval-Augmented Generation chatbot powered by **Phi-3/Gemini** and **Pinecone/Jina** allows employees to dynamically query company expense policies, ensuring adherence to financial guidelines before submission.
*   🔐 **Role-Based Access Control (RBAC):** Secures access to expense reports and financial data based on organizational hierarchy (e.g., Employee, Manager, Admin).
*   🏨 **Smart Cost Prediction:** Integrates the **Amadeus API** to predict hotel expenditures, helping to identify the most economical lodging options and enforce cost efficiency.
*   📊 **Comprehensive Reporting:** Automatically compiles validated expenses into detailed reports, highlighting irregularities and providing actionable financial insights.

### 🏗️ System Architecture & Workflow

```mermaid
flowchart TD
    %% User Roles & Access
    subgraph Users [Role-Based Access Control - RBAC]
        E[Employee]
        M[Manager / Admin]
    end

    %% Frontend Layer
    subgraph Frontend [Frontend Interface]
        UI[Next.js Web App]
        Chat[Policy Chatbot UI]
        Dashboard[Expense & Insight Dashboard]
    end

    %% Backend Layer
    subgraph Backend [Backend Services]
        Node[Node.js / Express API<br>Auth, Routing, Business Logic]
        Flask[Flask API<br>ML & Data Processing]
    end

    %% AI & ML Engine
    subgraph AIEngine [AI & ML Processing Engine]
        OCR[Paddle-OCRX<br>Receipt & Invoice Extraction]
        AutoEnc[AutoEncoders<br>Vector-Based Clustering / Anomaly Detection]
        RAG[RAG Pipeline<br>Jina Embeddings]
        LLM[Phi-3 / Gemini<br>Generative AI]
    end

    %% Databases
    subgraph Databases [Data Storage]
        Mongo[(MongoDB<br>Users, Reports, RBAC)]
        Pinecone[(Pinecone Vector DB<br>Company Policies)]
    end

    %% External APIs
    subgraph External [External APIs]
        Amadeus[Amadeus API<br>Hotel Price Prediction & Verification]
    end

    %% User Interactions
    E -->|Uploads Receipts| UI
    E -->|Queries Policies| Chat
    M -->|Reviews Flagged Reports| Dashboard
    UI & Chat & Dashboard --- Node

    %% Backend Routing
    Node <-->|CRUD & Auth| Mongo
    Node <-->|Offloads Heavy Compute| Flask

    %% ML Processing Flow
    Flask -->|1. Extract Text| OCR
    OCR -->|Extracted Data| AutoEnc
    AutoEnc -->|2. Flag Anomalies| Node

    %% Chatbot RAG Flow
    Flask <-->|3. Retrieve Context| RAG
    RAG <--> Pinecone
    RAG <--> LLM
    LLM -->|Answers Queries| Chat

    %% Cost Optimization Flow
    Flask <-->|4. Fetch Lodging Data| Amadeus
    Amadeus -->|Compare with Claims| AutoEnc

    %% Output
    Node -->|5. Generate Final Report| Dashboard

    %% Styling
    classDef frontend fill:#e1f5fe,stroke:#0288d1,stroke-width:2px;
    classDef backend fill:#fff3e0,stroke:#f57c00,stroke-width:2px;
    classDef ai fill:#e8f5e9,stroke:#388e3c,stroke-width:2px;
    classDef db fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px;
    classDef ext fill:#eceff1,stroke:#607d8b,stroke-width:2px;

    class UI,Chat,Dashboard frontend;
    class Node,Flask backend;
    class OCR,AutoEnc,RAG,LLM ai;
    class Mongo,Pinecone db;
    class Amadeus ext;
```

## 🛠️ Technology Stack

Fraud Zero is built on a robust, scalable, and AI-centric technology stack:

### Frontend & Backend
*   **Frontend:** Next.js (React)
*   **Backend:** Node.js (Express), Python (Flask)
*   **Database:** MongoDB

### Artificial Intelligence & Machine Learning
*   **OCR Engine:** Paddle-OCRX (for high-accuracy receipt parsing)
*   **Large Language Models (LLMs):** Phi-3, Google Gemini
*   **Vector Database (RAG):** Pinecone, Jina
*   **Anomaly Detection:** AutoEncoders (for vector-based clustering of spending patterns)

### External Integrations
*   **APIs:** Amadeus API (for hotel booking and expenditure prediction)

---
*Run smarter expense tracking. Streamline your expense management with real-time collaboration, track receipts, generate reports, and manage budgets from anywhere with FRAUD ZERO.*
