# Hybrid Search

**Summary:** iDempiere Hybrid Search is a plugin that enhances iDempiere's search capabilities by combining traditional full-text (lexical) search with modern vector (semantic) search. 
This approach, known as Hybrid Search, provides more relevant results by understanding both the specific keywords and the semantic meaning of the search query.

## 🚀 Features

- **Hybrid Search Engine**: Combines keyword-based search (PostgreSQL TSVector / Oracle Text) with vector similarity search for superior relevance.
- **Multiple Database Support**:
    - **PostgreSQL**: Utilizes `pgvector` for vector storage and similarity search, and optionally `pgai` for embedding generation.
    - **Oracle**: Supports Oracle's native search and vector capabilities.
- **Embedding Services**:
    - **Local ONNX**: Generate embeddings locally using ONNX models without external API dependencies.
    - **Database-side**: Leverage database-native embedding capabilities (e.g., PostgreSQL `pgai`).
- **Flexible Configuration**: Define search indices and columns directly within iDempiere's metadata.
- **Automatic Indexing**: Event-based updates ensure your search index stays synchronized with record changes.
- **Reciprocal Rank Fusion (RRF)**: Intelligently merges and ranks results from both lexical and semantic searches.

## ⚙️ Compatibility

* **iDempiere Version:** 13.0
* **Java Version:** 17+
* **Database:** PostgreSQL (Optimized), Oracle (Compatible)

## 📦 Database Changes

* **System PackIn:** This module includes a 2Pack intended for the System tenant to configure new Window and Field metadata. Add `HybridSearch` **Search Type**.
* **Example Tenant PackIn:** 
- **Business Partner Hybrid Search**: [examples/BPartnerSearches.zip](examples/BPartnerSearches.zip)
- **Application Menu Hybrid Search**: [examples/MenuSearches.zip](examples/MenuSearches.zip)

## 🛠 Usage & Configuration

See https://github.com/hengsin/idempiere-hybrid-search?tab=readme-ov-file#setup-and-configuration

## 📸 Screenshots

![Business Partner Search Column](assets/Business%20Partner%20Search%20Column.png)

## 👤 Author / Support

* **Developer:** [https://github.com/hengsin](https://github.com/hengsin)
* **Source Code:** [https://github.com/hengsin/idempiere-hybrid-search](https://github.com/hengsin/idempiere-hybrid-search)
* **Issue Tracker:** [https://github.com/hengsin/idempiere-hybrid-search/issues](https://github.com/hengsin/idempiere-hybrid-search/issues)
