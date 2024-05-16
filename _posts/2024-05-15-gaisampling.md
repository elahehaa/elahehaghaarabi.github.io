---
title: 'Sampling Techniques in Generative Language Models'
date: 2024-05-15
permalink: /posts/2024/05/generative-language-models-sampling/
tags:
  - Transformer-based Language Models
  - Generative AI
---

Generative language models employ various sampling techniques to select the next token, each influencing the diversity and coherence of generated sequences. These techniques include:

## Greedy Sampling
The model selects the token with the highest probability at each step. While computationally efficient, it often leads to repetitive and less diverse outputs.

Example:
Given the following probability distribution for the next token:
- Token A: 0.6
- Token B: 0.3
- Token C: 0.1

Greedy sampling would select Token A because it has the highest probability, resulting in a predictable sequence.

## Top-k Sampling
This method restricts sampling to the top-k tokens with the highest probabilities, where k is a predetermined value. It introduces more diversity compared to greedy sampling while still maintaining some control over the generated sequence.

Example:
Given the same probability distribution as above and setting k=2, top-k sampling would consider only Token A and Token B. The model randomly selects one of these tokens based on their probabilities, resulting in a more varied output.

## Top-p Sampling (Nucleus Sampling)
Also known as nucleus sampling, this technique involves selecting tokens from the smallest set whose cumulative probability exceeds a certain threshold, p. It dynamically adjusts the set of candidate tokens based on their probabilities.

Example:
Consider a probability distribution with many tokens, where the cumulative probability of the top tokens exceeds a threshold of 0.8. Nucleus sampling would select tokens from this subset, ensuring both diversity and coherence in the generated text.

## Temperature Scaling
Temperature scaling modifies the logits produced by the model before applying the softmax function. By dividing logits by a temperature parameter, the distribution of probabilities is adjusted. A temperature < 1 emphasizes high-probability tokens, while a temperature > 1 encourages diversity by smoothing the distribution.

Example:
Given the same probability distribution as above, applying temperature scaling with a value of 0.5 would amplify the differences between probabilities. As a result, Token A, with its higher probability, would be even more likely to be chosen, leading to a more deterministic output.
