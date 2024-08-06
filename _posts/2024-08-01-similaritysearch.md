---
title: 'Similarity Search'
date: 2024-08-01
permalink: /posts/2024/02/h/
tags:
  - Transfornmer-based Language Models
  - Embeddings
  - Re-ranking
  - Similarity Search
  - Information Retrieval
  - Cross-encoders
  - Bi-encoders
---




In the process of creating a knowledge base to guide generative language models, a robust framework should be established to index, retrieve, 
and rank top similar items efficiently at scale. The framework should return the top similar documents for the user's query with high recall and precision.

## Bi-encoder
When a user initiates a query, the first step is to compare the user query with all documents available in the knowledge base and calculate a similarity score for each pair of
(query, knowledge base item). A bi-encoder is ideal for this step as it aims to find as many relevant documents as possible from the knowledge base. 
In other words, the goal is to maximize recall (the ratio of detected relevant documents to the total number of relevant documents available). 
A bi-encoder independently generates embeddings for the query and the documents in the knowledge base and then uses a similarity measure like cosine similarity to 
calculate the similarity score.
## Cross-encoder
The next step is to improve the precision of the framework. While the bi-encoder guarantees high recall, it may result in low precision. 
To increase precision, an additional step is added to the framework to identify relevant documents more accurately.
Precision is the ratio of retrieved relevant documents to the total number of documents retrieved. A cross-encoder can generate embeddings of the query and document together, 
which helps capture the context and relationship between the two and increases the likelihood of identifying truly relevant documents. 
It essentially acts as a classifier on top of an embedding layer that predicts the similarity score.![Screenshot from 2024-08-06 12-46-33](https://github.com/user-attachments/assets/0f1f41d2-d09b-46c1-931c-2ba2a10433ba)

It should be noted that the cross-encoder is a more computationally expensive process, as the model needs to generate embeddings for combinations of each pair of sentences.

