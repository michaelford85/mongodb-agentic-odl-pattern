# 🌐 Agentic-ODL-Pattern: The Operational Data Layer for AI Agents

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/Agentic-ODL-Pattern/blob/main/notebooks/agentic_odl_demo.ipynb)

https://colab.research.google.com/github/michaelford85/atlas-rag-pipeline/blob/main/atlas_rag_pipeline.ipynb

## 📌 Overview

This repository provides a reference architecture for the **Operational Data Layer (ODL)**—the "connective tissue" between fragmented enterprise data and the reasoning capabilities of **Agentic AI**.

In modern AI architectures, agents often fail because they lack real-time context, suffer from "memory loss" between sessions, or cannot access unstructured data alongside transactional records. This project demonstrates how **MongoDB Atlas** serves as a unified ODL to provide:

1.  **Unified Source of Truth:** Harmonizing structured, semi-structured, and vector data.
2.  **Long-Term Agent Memory:** Persisting agent reasoning, tool-call history, and user preferences.
3.  **Real-Time Context:** Using Change Streams to trigger agentic workflows based on live data events.

---

## 🏗️ The Architecture

Unlike traditional RAG (Retrieval-Augmented Generation) which often relies on static PDFs, an **Agentic ODL** allows the AI to interact with a living database:

* **Vector Search:** For semantic retrieval of documents, notes, and history.
* **Flexible Schema:** To ingest diverse data sources (IoT, SQL, Logs) without rigid ETL.
* **Metadata Filtering:** To ground AI responses in "hard facts" (e.g., current policy status or regional laws).

---

## 🏎️ Industry Spotlight: Car Insurance
While the ODL pattern is universal, this repository includes a "Flavor Module" for **Automotive Insurance** to illustrate the business impact:

- **The Problem:** Claims adjusters spend 40% of their time toggling between policy databases, telemetry logs, and manual damage photos.
- **The ODL Solution:** An AI Agent queries the ODL to instantly correlate a driver's braking telemetry with their policy coverage and similar historical claims to suggest an automated settlement.

---

## 🚀 Getting Started with Google Colab

The easiest way to explore this pattern is through our interactive Jupyter Notebook.

1.  **Launch the Notebook:** Click the "Open in Colab" badge at the top of this page.
2.  **Configuration:** You will need a MongoDB Atlas Connection String and an OpenAI API Key.
3.  **Data Generation:** The notebook includes a synthetic data engine that generates:
    * **Customer Profiles** (Structured)
    * **Vehicle Telemetry** (Time-series/IoT)
    * **Adjuster Notes** (Unstructured/Vector-ready)

---

## 🛠️ Key Components

| Component | Role in Agentic AI | MongoDB Feature |
| :--- | :--- | :--- |
| **Context Store** | Provides the agent with a "360-degree view" of the entity. | Document Model |
| **Semantic Memory** | Allows agents to find "similar situations" from the past. | Atlas Vector Search |
| **Operational State** | Tracks the agent's current task list and "thoughts." | ACID Transactions |
| **Event Trigger** | Notifies the agent when a specific data threshold is met. | Change Streams |

---

## 📂 Repository Structure

```text
├── notebooks/
│   └── agentic_odl_demo.ipynb    # Main Google Colab demonstration
├── src/
│   ├── generator.py              # Synthetic data engine
│   ├── agent_logic.py            # LangChain/CrewAI agent definitions
│   └── atlas_client.py           # MongoDB connection helpers
├── data/
│   └── industry_flavors/         # JSON templates for different verticals
└── README.md

## Contributing

This pattern is designed to be extensible. If you would like to add an industry module (e.g., Healthcare, Retail, or Supply Chain), please submit a Pull Request.

## License

Apache 2.0