# Decoding Strategies: Temperature, Top-K, and Top-P

## 1. What Is Decoding?

A language model generates text by repeatedly predicting the next token.

For example, given:

> Today, I am feeling...

The model may assign probabilities to possible next tokens:

| Token | Example Probability |
|---|---:|
| happy | 40% |
| good | 25% |
| tired | 20% |
| hungry | 10% |
| airplane | 5% |

These probabilities are illustrative. Actual probabilities depend on the model and context.

**Decoding** is the process of selecting the next token from the model's predicted distribution.

Decoding strategies control how the model selects tokens and how diverse or predictable its output tends to be.

The three common controls are:

- Temperature
- Top-K sampling
- Top-P sampling

## 2. Temperature

Temperature controls the sharpness of the token probability distribution.

It is applied to the model's logits before converting them into probabilities using softmax.

Conceptually:

- **Low temperature:** Makes the distribution more concentrated around high-probability tokens.
- **High temperature:** Makes the distribution flatter, giving lower-probability tokens relatively more chance of being selected.
- **Temperature of 1:** Leaves the logits at their original scale before softmax.

For a positive temperature, the probability calculation can be expressed as:

\[
P_i = \frac{e^{z_i/T}}{\sum_j e^{z_j/T}}
\]

Where:

- \(z_i\) is the logit for token \(i\).
- \(T\) is the temperature.
- \(P_i\) is the resulting probability.

### Example

For the same prompt:

- A low temperature often produces more predictable wording.
- A moderate temperature allows some variation.
- A high temperature can produce more diverse but potentially less coherent output.

Temperature does not directly change the model's knowledge or intelligence. It changes the probability distribution used during token selection.

## 3. Top-K Sampling

Top-K sampling restricts the candidate tokens to the K tokens with the highest probabilities.

For example, suppose the model predicts:

| Token | Probability |
|---|---:|
| happy | 40% |
| good | 25% |
| tired | 20% |
| hungry | 10% |
| airplane | 5% |

If `K = 3`, only these candidates remain:

- happy
- good
- tired

The remaining candidates are excluded from sampling, and the retained probabilities are renormalized.

### Key points

- `K = 1` retains only the highest-probability token.
- A small K restricts the number of possible next tokens.
- A larger K allows more candidate tokens.
- Top-K uses a fixed number of candidates, regardless of how their probabilities are distributed.

## 4. Top-P Sampling

Top-P sampling is also known as **nucleus sampling**.

Instead of retaining a fixed number of tokens, it retains the smallest group of highest-probability tokens whose cumulative probability reaches or exceeds the selected threshold P.

Using the previous example:

| Token | Probability | Cumulative Probability |
|---|---:|---:|
| happy | 40% | 40% |
| good | 25% | 65% |
| tired | 20% | 85% |
| hungry | 10% | 95% |
| airplane | 5% | 100% |

If `P = 0.90`, the retained group contains happy, good, tired, and hungry because their cumulative probability reaches 95%. Airplane is excluded.

The probabilities of the retained tokens are renormalized before sampling.

### Key points

- A lower Top-P threshold usually restricts the candidate group more strongly.
- A higher Top-P threshold usually permits more candidates.
- `P = 1` normally retains the full probability distribution.
- The number of retained tokens can change depending on the probability distribution.

## 5. Top-K vs. Top-P

| Feature | Top-K | Top-P |
|---|---|---|
| Selection rule | Fixed number of highest-probability tokens | Smallest group reaching a cumulative probability threshold |
| Number of candidates | Fixed by K | Varies with the distribution |
| Main purpose | Limit the candidate set | Adapt the candidate set to the distribution |
| Alternative name | K-based sampling | Nucleus sampling |

## 6. How They Work Together

A generation system may combine temperature with Top-K or Top-P sampling.

For example:

1. The model calculates logits for possible next tokens.
2. Temperature adjusts the probability distribution.
3. A sampling filter may restrict the candidate tokens using Top-K or Top-P.
4. The system samples a token from the remaining distribution.
5. The process repeats to generate the next token.

The exact order can differ between implementations.

## 7. Practical Takeaways

- Use lower temperature when more predictable output is desirable.
- Use higher temperature when more variation is desirable.
- Use Top-K to restrict sampling to a fixed number of likely candidates.
- Use Top-P to retain candidates based on cumulative probability.
- These controls influence generation behavior; they do not guarantee factual accuracy or creativity.

**In one sentence:**

Temperature controls the shape of the probability distribution, Top-K limits the number of candidate tokens, and Top-P limits candidates based on cumulative probability.
