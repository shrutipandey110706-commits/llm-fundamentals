# Positional Encoding and Where Facts Live

**Learning Resource:** Phillip Lacner — LLM Fundamentals

# Part 1: Positional Encoding

## 1. What Is Positional Encoding?

Positional encoding is a method of providing information about token positions to a Transformer.

Token order matters because the same words in a different order can express different meanings.

For example:

- `The dog chased the cat.`
- `The cat chased the dog.`

The words are similar, but their order changes who chased whom.

## 2. Why Is Positional Information Important?

Token embeddings represent tokens numerically, but the model also needs information about their positions in the sequence.

Positional information helps the model distinguish different token orders and process relationships in context.

## 3. How Does It Work?

In the original Transformer architecture, positional encodings are added to token embeddings before the representations enter the Transformer layers.

Other architectures use alternative approaches, including learned positional embeddings and rotary positional embeddings.

Therefore, not every modern LLM uses the same positional-information method.

## 4. Key Takeaways

- Token order can change meaning.
- Positional information helps Transformers account for token positions.
- The original Transformer used positional encodings added to token embeddings.
- Modern Transformer architectures may use different positional methods.

# Part 2: Where Do Facts Live in an LLM?

## 5. Where Does a Model Learn Facts?

During training, an LLM adjusts its learned parameters, commonly called weights, using training data.

Information and patterns learned during training can be encoded in these parameters. They are generally distributed across the network rather than stored as a simple table containing one row per fact.

For example, a model may learn the association between France and Paris from training data.

However, it does not necessarily store that fact in one identifiable parameter or neuron.

## 6. Three Sources That Can Influence an Answer

### A. Model Weights

The trained parameters encode patterns and information learned during training.

### B. Prompt and Conversation Context

The current input provides information that influences the model's response.

### C. External Information

A system can retrieve additional information using search tools, databases, or Retrieval-Augmented Generation (RAG).

The final answer may depend on all three sources.

## 7. Training, Inference, and RAG

- **Training:** Adjusts model parameters to learn patterns from data.
- **Inference:** Uses the trained model to generate an answer from the current input.
- **RAG:** Retrieves relevant external information and supplies it as context to the model.

RAG is useful when an application needs information that may not be present in the model's learned parameters, such as updated company policies or college placement notices.

## 8. Important Considerations

- Learned information is not generally stored as a simple fact database inside the model.
- Model weights can encode information in distributed and complex ways.
- A model may produce incorrect or outdated answers.
- External retrieval can provide relevant information but does not guarantee that the final answer is correct.

## 9. Key Takeaways

- Positional information helps a Transformer process token order.
- Model weights encode patterns learned during training.
- A fact is not necessarily stored in one specific neuron.
- Prompts and external retrieval can also influence generated answers.
- RAG connects information retrieval with LLM generation.

## 10. What I Learned

I learned why Transformers need positional information and how learned model weights can encode patterns and facts. I also understood the difference between training, inference, and retrieving external information through RAG.

