---
title: 'Addressing LLM Hallucination'
date: 2024-05-01
permalink: /posts/2024/02/h/
tags:
  - Transfornmer-based Language Models
  - Generative AI
  - Information Retrieval
  - Vector Database
  - Retrieval-Augmented Generation
---




Language models often produce irrelevant, non-factual, and synthetic answers when responding to user queries. This issue, known as hallucination in the field of GenAI, becomes particularly critical when applied in the healthcare domain. To mitigate this problem, we can employ different techniques to guide the LLM to generate more accurate responses.

## 1. Retrieval Augmented Generation (RAG)
Retrieval Augmented Generation (RAG) combines the strengths of retrieval-based and generation-based models to enhance the accuracy and relevance of responses. 
To address language model hallucination in a sensitive context like medical question answering, we designed a platform to guide the model toward providing more relevant and accurate answers.

### Building a Knowledge Base

BlueBERT is a BERT model pre-trained on PubMed abstracts and clinical notes, combining both biomedical and clinical domain knowledge. The pre-trained model is used to generate embeddings from the titles and abstracts of pre-selected PubMed publications. This knowledge is stored and indexed in a vector database, Pinecone, which retrieves data based on the top-k most similar documents. The plan is to enrich the knowledge base with clinical notes in the future.

### Query Expansion

Retrieval-Augmented Generation (RAG) is used as a query expansion technique. When a user asks a question (query), the same language model (BlueBERT) that generated embeddings for the knowledge base is used to generate an embedding for the query.
The query embedding is then used to retrieve the top-k related documents from the knowledge base, which is typically a vector database (Pinecone) that stores the document embeddings and allows efficient nearest neighbor search based on cosine similarity.
A prompt is designed to expand the query and guide the generative language model (GPT) in generating a relevant answer. The prompt takes the following format: "Given the following context, answer the question that follows using only the information provided in the context. Context: [Retrieved Passages] Question: [Original Query]".

## 2. LLM Function Calling
Another technique to guide language models toward generating more accurate results is by employing models fine-tuned on function calling tasks. By integrating specific functions, the language model is directed to extract and utilize precise information from input and generate responses in a structured manner. This approach also enables the model to access more recent or updated information from external sources, such as the web.

For instance, to enhance the accuracy and comprehensiveness of answers to medical questions regarding drugs, the model can utilize the NLM drug database through RESTful requests. By doing so, the GPT model is guided to answer questions using the retrieved data, ensuring that the responses are both up-to-date and highly relevant. This method not only mitigates hallucinations but also significantly improves the reliability and factual correctness of the generated content. An implementation of this framework can be found [here]().

## 3. Lookback Lens
The Lookback guided decoding technique involves a pre-trained classifier that adds an additional layer of sampling to LLMs to identify and exclude hallucinated tokens from the final selection. This technique is elaborated in this [repo](https://github.com/voidism/Lookback-Lens).









<!-- You can have many headings
======
-->

<!-- Aren't headings cool?
------ -->
