# Tokenization

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. What Is Tokenization?

Tokenization is the process of splitting text into smaller units called **tokens** so that a language model can process it.

A token can represent a complete word, part of a word, punctuation, or another text unit.

For example, the word `playing` might be split into `play` and `ing`. The exact split depends on the tokenizer.

## 2. Word-Based Tokenization

In word-based tokenization, each word is assigned its own token ID.

### Limitation

- The vocabulary can become extremely large.
- Different word forms, names, technical terms, slang, and spelling variations are difficult to cover.
- A word missing from the vocabulary can cause an unknown-word problem.

## 3. Character-Based Tokenization

In character-based tokenization, each character becomes a separate token.

For example:

`cat` → `c` + `a` + `t`

### Advantages

- A small character vocabulary can represent many words.
- Unfamiliar words can be represented using known characters.

### Limitations

- Text sequences become much longer.
- Longer sequences can increase computational costs.
- The model must learn relationships between individual characters as well as higher-level language patterns.

## 4. Subword Tokenization

Subword tokenization divides text into reusable pieces that are smaller than words but often larger than individual characters.

For example:

`playing` → `play` + `ing`

This is an illustrative example; the exact representation depends on the tokenizer.

### Advantages

- Keeps the vocabulary more manageable than a full word-level vocabulary.
- Usually produces shorter sequences than character-level tokenization.
- Allows unfamiliar words to be represented using combinations of known pieces, provided the tokenizer supports the required fallback units.

## 5. Vocabulary and Token IDs

- **Vocabulary:** The collection of tokens supported by a tokenizer.
- **Token ID:** The numerical identifier assigned to a token.
- **Sequence Length:** The number of tokens representing an input.

## 6. Connection to Attention

Transformers process sequences of tokens. In standard self-attention, computation and memory can scale approximately quadratically with sequence length.

Therefore, tokenization affects how much text can fit into a context window and how efficiently it can be processed.

## 7. Key Takeaways

- Tokenization converts text into manageable units.
- Word-based tokenization can require a very large vocabulary.
- Character-based tokenization can produce very long sequences.
- Subword tokenization balances vocabulary size and sequence length.
- Tokenization affects the efficiency of language-model processing.

## 8. What I Learned

I learned why word-based and character-based tokenization have limitations, how subword tokenization addresses these challenges, and why vocabulary size and sequence length matter for LLMs.
