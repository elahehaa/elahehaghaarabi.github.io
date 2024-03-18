---
title: 'Static Embedding Techniques'
date: 2024-01-08
permalink: /posts/2024/01/s/
tags:
  - Word2Vec
  - FastText
  - Universal Embedding 
  - GloVe
  - Text Embedding
---

Before the publication of the "Attention is All You Need" paper and the introduction of attention mechanisms and transformers, static embeddings were extensively employed to convert text data into numerical representations, creating features for deep learning and sequential neural network models such as RNNs and LSTMs. This section provides a brief summary of well-known embedding techniques.

Static embeddings are typically created using shallow neural networks such as skip-gram or continuous bag of words (CBOW). These neural networks are trained using unsupervised learning techniques to generate a fixed-size numerical vector for each word in the vocabulary of the training corpus. Ideally, these vectors should capture the semantics of the text, meaning that words with similar meanings are close together in the vector space. However, they are unable to capture context, and as a result, a word with different meanings may have the same vector representation.

## Word2Vec

This method was introduced by Mikolov et al. in their 2013 paper titled 'Efficient Estimation of Word Representations in Vector Space.' Word representations in the form of vectors can be learned through unsupervised learning using a shallow neural network. In the skip-gram architecture, the model predicts context words based on a target word within a specified window size. CBOW (Continuous Bag of Words) is another architecture used in Word2Vec, which predicts the target word based on the context words surrounding it.

[BioWordVec](https://github.com/ncbi-nlp/BioSentVec/blob/master/README.md) is a model trained using PubMed and MIMIC-III data by researchers at NIH (National Institutes of Health). It is specifically pre-trained for use in the biomedical domain.

## FastText

FastText is an extension of the Word2Vec model. By incorporating n-grams into the model, it provides flexibility to handle out-of-vocabulary words (OOV). Essentially, FastText segments words into subwords and aggregates the vectors for each subword. Additionally, FastText addresses morphology issues by considering subword information, which aids in capturing morphological variations and improving the model's performance. This method is introduced by Mikolov et al. in their 2018 paper titled 'Advances in Pre-Training Distributed Word Representations'.

## GloVe

'GloVe: Global Vectors for Word Representation' introduced by Jeffrey Pennington, Richard Socher, and Christopher D. Manning in 2014, presents another approach to representing words in a vector space, capturing both syntactic and semantic aspects of text. The algorithm learns word embeddings by considering the global co-occurrence statistics of words in a corpus. It constructs a co-occurrence matrix, where each cell denotes the frequency of a word appearing in the context of another word. Subsequently, the algorithm factorizes this matrix to derive low-dimensional vector representations for words.

![Screenshot from 2024-03-18 15-29-45](https://github.com/elahehaghaarabi/elahehaghaarabi.github.io/assets/30157012/9f3e5047-aade-47ec-a27a-c317f8b440b6)
Copy code
