# Multi-Head Attention

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. What Is Multi-Head Attention?

Multi-head attention is a Transformer mechanism that performs multiple attention operations in parallel.

Each attention head uses its own learned query, key, and value projections. This allows the model to learn different patterns of relationships from the same input.

## 2. Example

Consider the sentence:

`Shruti learned Java because she wants a software job.`

Different attention heads may learn patterns involving:

- Relationships between names and pronouns.
- Relationships between actions and their objects.
- Relationships between technical terms and surrounding words.

These are illustrative possibilities. Individual attention heads do not necessarily correspond to one specific human-interpretable relationship.

## 3. How Does It Work?

A simplified process is:

1. The same input representations are passed to multiple attention heads.
2. Each head calculates attention using its own learned projections.
3. Each head produces an output representation.
4. The head outputs are concatenated.
5. A learned output projection combines them into the final multi-head attention output.

## 4. Self-Attention vs. Multi-Head Attention

- **Self-attention:** Calculates relationships between tokens using query, key, and value representations.
- **Multi-head attention:** Runs multiple attention heads in parallel and combines their outputs.

Multi-head attention uses the self-attention operation as a building block.

## 5. Why Is Multi-Head Attention Useful?

It gives the model multiple learned ways to process relationships between tokens. The combined outputs can provide richer contextual representations than a single attention head alone.

## 6. Key Takeaways

- Multi-head attention contains multiple attention heads.
- Each head has its own learned projections.
- Heads calculate attention in parallel.
- Their outputs are combined into one representation.

## 7. What I Learned

I learned that multi-head attention allows Transformers to process token relationships through multiple parallel attention calculations. The resulting outputs are combined to help build contextual representations.
