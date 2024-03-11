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

1 - Byte Pair Encoding (BPE) is an algorithm based on the UTF-8 byte system, utilized for compressing data by merging the most frequent tokens. Popular language models like GPT-2, RoBERTa, and XLNet use BPE in their tokenizers. You can experiment with different models' tokenizers [here](https://tiktokenizer.vercel.app/). 

A simple implementation of the algorithm can be found [here](https://github.com/elahehaghaarabi/language_model_tokenizers/blob/main/bpe.ipynb).

To implement the algorithm, the following steps are required:

  * UTF-8 encoding is used to convert single characters to codes. The maximum allowed vocabulary size in UTF-8 is 256, which results in a large embedding dimension. Consequently, the context window size, limited to a predefined value, won't cover a lot of information. Therefore, a larger vocabulary size (as a hyperparameter) is selected and trained.
  * Iteratively, find pairs of tokens with higher occurrence and merge them into a single token, appending them to our vocabulary.


<!-- Headings are cool
======
-->

<!-- You can have many headings
======
-->

<!-- Aren't headings cool?
------ -->
