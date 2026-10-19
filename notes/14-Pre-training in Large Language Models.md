# Pre-training in Large Language Models (LLMs)

## 1. What Is Pre-training?

Pre-training is the initial training stage in which a language model learns general language patterns and useful representations from a large collection of text and other training data.

The data may include books, articles, websites, code, and other text sources.

During pre-training, the model adjusts its numerical parameters (weights) to improve its predictions.

## 2. Next-Token Prediction

A common pre-training objective for autoregressive language models is next-token prediction.

The model receives a sequence of tokens and learns to predict the next token.

**Example:**

Input: `The sun rises in the`

Expected continuation: `east`

The model predicts a distribution of possible next tokens. A training objective measures how well its predictions match the target tokens, and optimization updates the model's parameters.

This process is repeated across many training examples.

## 3. What Does the Model Learn?

Pre-training can help a model learn:

- Grammar and sentence structure.
- Vocabulary and language patterns.
- Relationships between words and concepts.
- Patterns found in factual text.
- Code and other structured text patterns, when included in training.

Pre-training does not guarantee that every learned fact will be recalled correctly.

## 4. What Is a Base Model?

A model after pre-training is commonly called a **base model** or **pre-trained model**.

A base model can generate text, but it may not reliably behave like a helpful assistant or follow every user instruction.

Additional training can adapt it for instruction following and conversational tasks.

## 5. Pre-training vs. Fine-Tuning

| Pre-training | Fine-tuning |
|---|---|
| Learns broad patterns from large-scale data. | Adapts an existing model using more targeted examples. |
| Often uses next-token prediction. | Uses an objective suited to the target task. |
| Produces a base model. | Can improve instruction following or specialized performance. |

## Key Takeaway

Pre-training gives a language model its broad foundation by learning patterns from data. It is an important starting point for building many modern LLMs, but it does not automatically make the model a reliable assistant.
