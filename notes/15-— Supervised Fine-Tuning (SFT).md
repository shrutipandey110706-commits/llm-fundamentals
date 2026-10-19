# Supervised Fine-Tuning (SFT)

## 1. What Is SFT?

**Supervised Fine-Tuning (SFT)** is a training method that adapts a pre-trained model using curated examples of desired behavior.

For instruction-following language models, these examples often contain an instruction or prompt and a high-quality response.

SFT helps a model learn how to respond to instructions rather than merely continue arbitrary text.

## 2. Example of SFT

**Prompt:**

Explain photosynthesis in simple words.

**Desired response:**

Photosynthesis is the process by which plants use sunlight, water, and carbon dioxide to make their food.

The model is trained on examples like this so that it becomes better at producing appropriate responses to similar instructions.

## 3. How Does SFT Work?

1. Start with a pre-trained model.
2. Prepare a dataset containing prompts and desired responses.
3. Feed the examples to the model.
4. Compare the model's predictions with the target response tokens using a training objective.
5. Update the trainable parameters to improve the predictions.
6. Evaluate the resulting model on suitable test examples.

Depending on the training setup, some or all model parameters may be updated.

## 4. What Can SFT Teach?

SFT can help a model learn to:

- Follow user instructions.
- Answer questions clearly.
- Summarize long text.
- Translate between languages.
- Explain concepts at different levels.
- Follow requested output formats.
- Produce examples of desired assistant behavior.

The quality and coverage of the training examples strongly affect the result.

## 5. Pre-training vs. SFT

| Pre-training | SFT |
|---|---|
| Learns broad patterns from large-scale data. | Learns from curated examples for specific behaviors or tasks. |
| Commonly uses next-token prediction over training text. | Commonly predicts the desired response tokens for each example. |
| Produces a general base model. | Adapts the model to follow instructions and respond in desired ways. |

## Key Takeaway

Pre-training helps a model develop broad language capabilities. SFT uses examples of desired responses to make those capabilities more useful for instructions and conversations.

SFT alone does not guarantee that every answer will be correct, helpful, or safe.
