# The Math Behind LLMs Simplified

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. Introduction

Large Language Models use mathematical operations to process input text, learn patterns, and generate responses.

Although the mathematics inside modern LLMs can be complex, the basic workflow can be understood step by step.

## 2. Step 1: Convert Text into Numerical Representations

When a user enters text, the tokenizer divides it into tokens.

Each token is assigned a token ID, which is mapped to an embedding vector.

These vectors provide numerical representations that the neural network can process.

## 3. Step 2: Perform Mathematical Calculations

The model processes vectors through neural-network layers using mathematical operations.

Important concepts include:

- **Weights:** Learned numerical parameters that influence the model's computations.
- **Matrix multiplication:** An operation used to combine and transform numerical information efficiently.
- **Activation functions:** Functions that help neural networks model complex patterns.
- **Attention:** A mechanism that helps Transformer models process relationships between tokens.

These operations transform the input representations as they pass through the model.

## 4. Step 3: Process Context Using Attention

The meaning of a token can depend on the surrounding words.

For example:

`The cat sat on the mat because it was tired.`

Understanding the reference of `it` requires considering the sentence's context.

Attention helps Transformer-based models calculate relationships between tokens and incorporate relevant contextual information.

## 5. Step 4: Predict the Next Token

After processing the input, the model produces scores for possible next tokens. These scores can be converted into probabilities.

A decoding method then selects the next token according to the model's output and the generation settings.

The process repeats until the response is complete or a stopping condition is reached.

## 6. The Overall Workflow

Text → Tokenization → Token IDs → Embedding Vectors → Neural-Network Calculations → Context Processing → Next-Token Prediction

## 7. Key Takeaways

- LLMs represent text numerically before processing it.
- Vectors and matrices are important for neural-network calculations.
- Learned weights influence how information is transformed.
- Attention helps Transformer models process contextual relationships.
- LLMs generate text by repeatedly predicting the next token.

## 8. What I Learned

I learned that LLMs rely on mathematical operations to process text and generate responses. Tokenization and embeddings prepare the input, while neural-network calculations and attention help the model process context and predict subsequent tokens.
