---
title: 'NLP Must-Reads'
date: 2024-02-19
permalink: /posts/2024/02/n/
tags:
  - Natural Language Processing
  - Transfornmer-based Language Models
  - Contextualized Embedding
  - Computational Linguistics
  - Language Understanding
  - Generative AI
---

Here is an archive of major publications in the field of NLP, providing a historical overview of the discipline.

# Publications

## W2Vec

The term "word2vec" was introduced in the paper titled "Distributed Representations of Words and Phrases and their Compositionality," written by Tomas Mikolov, Ilya Sutskever, Kai Chen, Greg S. Corrado, and Jeffrey Dean. This paper was presented at the Neural Information Processing Systems (NeurIPS) conference in 2013.

W2Vec is a group of shallow neural network models trained to reconstruct linguistic contexts of words. The word2vec models efficiently learn distributed representations (embeddings) of words in a continuous vector space, capturing semantic relationships between words. This paper has had a significant impact on natural language processing and has become one of the foundational works in the field of word embeddings.

Mikolov, T., Sutskever, I., Chen, K., Corrado, G. S., & Dean, J. (2013).
[Distributed Representations of Words and Phrases and their Compositionality](https://arxiv.org/abs/1310.4546).
In Advances in neural information processing systems (NeurIPS), 26.

## ELMO

The "ELMo" (Embeddings from Language Models) paper is titled "Deep contextualized word representations" and was authored by researchers at Allen Institute for AI. The paper was presented at the Conference on Empirical Methods in Natural Language Processing (EMNLP) in 2018.

The main contribution of ELMo to the field of natural language processing (NLP) was the introduction of contextualized word representations. Prior to ELMo, traditional word embeddings methods, such as word2vec and GloVe, assigned a fixed vector to each word, regardless of its context within a sentence. ELMo addressed this limitation by providing embeddings that take into account the surrounding words and their relationships, resulting in context-dependent word representations.

Title: Deep contextualized word representations  
Authors: Matthew E. Peters, Mark Neumann, Mohit Iyyer, Matt Gardner, Christopher Clark, Kenton Lee, Luke Zettlemoyer  
Conference: Conference on Empirical Methods in Natural Language Processing (EMNLP)  
Year: 2018  
Paper Link: [ELMo](https://arxiv.org/abs/1802.05365)

ELMo varitions trained for biomedical text analysis include:

Title: Probing Biomedical Embeddings from Language Models  
Authors: Qiao Jin, Bhuwan Dhingra, William W. Cohen, Xinghua Lu  
Code: [BioELMo](https://www.catalyzex.com/paper/arxiv:1904.02181/code)  
Year: 2019  
Paper Link: [BioELMo](https://arxiv.org/abs/1904.02181)
