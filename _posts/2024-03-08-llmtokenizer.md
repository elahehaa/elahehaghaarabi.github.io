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

## Byte Pair Encoding
Byte Pair Encoding (BPE) is an algorithm based on the UTF-8 byte system, utilized for compressing data by merging the most frequent tokens. Popular language models like GPT-2, RoBERTa, and XLNet use BPE in their tokenizers. You can experiment with different models' tokenizers [here](https://tiktokenizer.vercel.app/). 

A simple implementation of the algorithm can be found [here](https://github.com/elahehaghaarabi/language_model_tokenizers/blob/main/bpe.ipynb).

To implement the algorithm, the following steps are required:

  * UTF-8 encoding is used to convert single characters to codes. The maximum allowed vocabulary size in UTF-8 is 256, which results in a large embedding dimension. Consequently, the context window size, limited to a predefined value, won't cover a lot of information. Therefore, a larger vocabulary size (as a hyperparameter) is selected and trained.
  * Iteratively, find pairs of tokens with higher occurrence and merge them into a single token, appending them to our vocabulary.

## WordPiece
WordPiece is a variant of the BPE algorithm, notably employed in the pre-training of BERT and several of its derivatives. While similar to BPE, WordPiece differs in its approach to token selection. Instead of relying solely on frequency, it calculates the ratio of a token's occurrence to that of its sub-tokens. The steps are as follows;
* Generating character tokens.
* Calculating the likelihood of occurrence for each pair.
* Selecting the pair with the maximum likelihood and merging tokens, adding it to the vocabulary.
* Repeating steps 2 and 3 until a pre-set vocabulary size is reached or the likelihood falls below a threshold.


## SentencePiece


