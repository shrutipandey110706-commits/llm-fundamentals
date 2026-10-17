# The Self-Attention Mechanism

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. What Is Self-Attention?

Self-attention is a mechanism that helps a Transformer process relationships between tokens in the same input sequence.

It allows the representation of a token to incorporate information from other relevant tokens.

## 2. Example

Consider the sentence:

`The animal didn't cross the road because it was tired.`

To interpret `it`, the model can use information from the word `animal` and the surrounding context.

Self-attention helps the model calculate which tokens contribute information when processing another token.

## 3. Query, Key, and Value

Self-attention uses three learned vector representations:

- **Query (Q):** Represents what a token is looking for when comparing information.
- **Key (K):** Represents information used to calculate how relevant another token is.
- **Value (V):** Contains information that contributes to the attention output.

These are mathematical representations, not literal questions or labels.

## 4. How Self-Attention Works

A simplified process is:

1. Input token representations are transformed into query, key, and value vectors.
2. Queries are compared with keys to calculate attention scores.
3. The scores are scaled and normalized into attention weights.
4. The weights determine how strongly each value vector contributes to the output.
5. The resulting representation incorporates information from other tokens.

In a standard scaled dot-product attention operation, the calculation is:

`Attention(Q, K, V) = softmax(QKᵀ / √dₖ)V`

Here, `dₖ` is the key-vector dimension.

## 5. Why Is Self-Attention Useful?

- It helps models incorporate contextual information.
- It calculates relationships between tokens.
- It supports processing long-range relationships within the available context.
- It helps Transformer models create context-aware token representations.

## 6. Key Takeaways

- Self-attention relates tokens to other tokens in a sequence.
- Queries and keys determine attention weights.
- Values provide information combined according to those weights.
- The resulting representations depend on context.

## 7. What I Learned

I learned that self-attention helps a Transformer determine how information from different tokens contributes to each token's updated representation. Query, key, and value vectors are central to this process.
