---
title: 'Large Language Model Tokenizers'
date: 2024-03-08
permalink: /posts/2024/03/l/
tags:
  - Transfornmer-based Language Models
  - Byte Pair Encoding
  - SentencePiece
  - Tokehnizer
---

Tokenizers are often overlooked in tutorials about LLMs, yet how they're trained significantly influences how the model comprehends text and domain knowledge. Let's briefly explore the five main types of tokenizers widely used in language models.

1 - Byte Pair Encoding (BPE) is an algorithm based on the UTF-8 byte system, utilized for compressing data by merging the most frequent tokens. Popular language models like GPT-2, RoBERTa, and XLMA use BPE in their tokenizers. You can play with different models' tokenizers [here](https://tiktokenizer.vercel.app/). A comparison of different languge model tokenizers in chuncking biomedical text can be found in another [post](todo)
A simple implementation of the algorithm can be found [here].

To implement the algorithm following steps are required;
 * utf-8 encoding is used to convert single characters to codes. The maximum allowed vocabulary size on utf-8 is 256 which makes a big embedding dimension and as a result the context window size, which is limited to a pre-defined value, won't cover a lot of information. As a result, a larger vocabulary size (as a hyperparameter) is selected and trained. 
 * Iteratively finding the pair of tokens with higher occurance and merge them to a single token and append to our vocabulary.


<!-- Headings are cool
======
-->

<!-- You can have many headings
======
-->

<!-- Aren't headings cool?
------ -->
