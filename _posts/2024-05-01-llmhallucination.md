---
title: 'LLM Hallucination in Healthcare'
date: 2024-05-01
permalink: /posts/2024/02/h/
tags:
  - Transfornmer-based Language Models
  - Generative AI
  - Information Retrieval
  - Vector Database
  - Retrieval-Augmented Generation
---



A semantic search and question answering system is designed to address language model hallucination in medical domain.

Language models often produce irrelevant, non-factual, and synthetic answers when responding to user queries. This issue, known as hallucination in the field of GenAI, becomes particularly critical when applied in the healthcare domain. To mitigate this problem, we employ the Retrieval Augmented Generation (RAG) technique to guide the model in generating relevant and accurate responses.

To address language model hallucination in a sensitive context like medical question answering, we designed a platform to guide the model toward providing more relevant and accurate answers.

### Building a Knowledge Base

BlueBERT is a BERT model pre-trained on PubMed abstracts and clinical notes, combining both biomedical and clinical domain knowledge. The pre-trained model is used to generate embeddings from the titles and abstracts of pre-selected PubMed publications. This knowledge is stored and indexed in a vector database, Pinecone, which retrieves data based on the top-k most similar documents. The plan is to enrich the knowledge base with clinical notes in the future.

### Query Expansion

Retrieval-Augmented Generation (RAG) is used as a query expansion technique. When a user asks a question (query), the same language model (BlueBERT) that generated embeddings for the knowledge base is used to generate an embedding for the query.
The query embedding is then used to retrieve the top-k related documents from the knowledge base, which is typically a vector database (Pinecone) that stores the document embeddings and allows efficient nearest neighbor search based on cosine similarity.
A prompt is designed to expand the query and guide the generative language model (GPT) in generating a relevant answer. The prompt takes the following format: "Given the following context, answer the question that follows using only the information provided in the context. Context: [Retrieved Passages] Question: [Original Query]".









<!-- You can have many headings
======
-->

<!-- Aren't headings cool?
------ -->
