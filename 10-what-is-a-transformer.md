# What Is a Transformer?

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. Introduction

A Transformer is a neural network architecture used by most modern Large Language Models (LLMs).

It helps models process token sequences and learn relationships between tokens in context.

## 2. How Does a Transformer Work?

A simplified Transformer-based LLM workflow is:

1. The tokenizer converts input text into tokens.
2. Token IDs are mapped to embedding vectors.
3. Positional information is incorporated into the token representations.
4. Transformer layers process the representations using attention and neural-network operations.
5. The model produces scores for possible next tokens.
6. A decoding method selects the next token, and generation continues.

## 3. Why Are Transformers Important?

Transformers use attention mechanisms to process relationships between tokens.

For example:

`The cat sat on the mat because it was tired.`

To interpret `it`, a model may use information from other tokens in the sentence.

Attention helps the model incorporate relevant contextual information instead of processing every token independently.

## 4. Important Components

- **Token embeddings:** Numerical representations of tokens.
- **Positional information:** Helps the model account for token order.
- **Self-attention:** Calculates relationships between tokens.
- **Multi-head attention:** Performs multiple attention calculations in parallel.
- **Feed-forward networks:** Further transform token representations.
- **Learned weights:** Parameters adjusted during training.

## 5. Key Takeaways

- A Transformer is a neural network architecture.
- It processes numerical representations of token sequences.
- Attention helps the model use contextual information.
- Transformer-based LLMs generate text by predicting subsequent tokens.

## 6. What I Learned

I learned that Transformers are a foundation of modern LLMs. They process token representations through attention and other neural-network operations to understand context and generate text.
