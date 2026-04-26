# 🌍 GEE Copilot: Neuro-Symbolic AI Compiler

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
![GEE](https://img.shields.io/badge/Google_Earth_Engine-API-green?style=for-the-badge&logo=google-earth)
![Architecture](https://img.shields.io/badge/Architecture-Neuro--Symbolic-purple?style=for-the-badge)
![Built By](https://img.shields.io/badge/Engineer-Mahmoud_Abdelsalam-orange?style=for-the-badge)

> **GEE Copilot** bridges the gap between natural language intent and the high-performance world of geospatial big data. By treating the interface as a **compilation task** rather than a standard chat interaction, the system achieves scientific-grade reliability for Google Earth Engine operations.

---

## 🧠 The Neuro-Symbolic Framework

Standard RAG systems often struggle with the rigid syntax of Geospatial APIs. This engine utilizes a **Dual-Layer Logic** to ensure 100% syntactical accuracy:

1.  **Neural Layer (Inference):** Interprets complex human semantics (e.g., *"How has the vegetation changed near the Nile Delta since last summer?"*).
2.  **Symbolic Layer (Compiler):** Validates intent against a strict **Domain-Specific Language (DSL)** and an immutable "Ground Truth" schema to generate executable code.

---

## 🚀 Key Technical Achievements

### 🏗️ From Chatbot to Compiler
Moving beyond simple text generation, the engine functions as a high-level compiler supporting:
* **Cross-Satellite Joins:** Seamlessly merging disparate datasets, such as **MODIS** wind data with **Sentinel-2** precipitation records.
* **Conditional Filtering:** Native support for multi-clause logic (e.g., `WHERE cloud_cover < 10%`).
* **Export Logic:** Integrated `INTO [filename]` syntax for automated data staging and processing.

### ⚖️ The "Optimizer" Protocol
Built-in logical guardrails evaluate requests before a single API call is made:
* **Resolution Awareness:** Automatically prioritizes **10m resolution** (Sentinel) over **500m** (MODIS) for local-scale spatial queries.
* **Domain Validation:** A spatial reasoning layer that rejects "Oceanic" datasets for land-locked queries, preventing expensive compute errors.

### 🛠️ Robust Data Engineering (The Ground Truth)
To eliminate hallucinations, I engineered a massive knowledge base:
* **Playwright ETL Pipeline:** Built a multi-threaded scraper to extract and structure **800+ pages** of GEE documentation.
* **Structured Schema:** Converted raw documentation into a machine-readable "Ground Truth" that the LLM references for valid function calls and parameters.

### ⛓️ Zero-Shot NER (Space & Time)
Replaced brittle external Geocoding/Date APIs with an in-context LLM parser:
* **Fuzzy Time Resolution:** Translates phrases like *"last summer"* or *"post-monsoon"* into precise Unix timestamps.
* **Location Semantics:** Resolves regional landmarks into exact bounding box coordinates in real-time.

---

## 📊 System Architecture

```mermaid
graph LR
    A[Natural Language Input] --> B{Neuro-Parser}
    B --> C[Zero-Shot NER]
    C --> D[Logic Optimizer]
    D --> E[DSL Compiler]
    E --> F[GEE Execution Engine]
    
    subgraph Knowledge_Base
    G[Playwright ETL Pipeline] --> H[(Structured Schema)]
    H --> D
    end
