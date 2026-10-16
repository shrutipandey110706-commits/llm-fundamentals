# Tokenization Algorithms: BPE, WordPiece, and SentencePiece

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. Byte Pair Encoding (BPE)

BPE is a subword tokenization algorithm that builds larger units by repeatedly merging frequent adjacent pairs.

### How It Works

1. Start with small units, such as characters or bytes.
2. Count adjacent pairs in the training data.
3. Merge a frequent eligible pair into a new unit.
4. Repeat the process according to the tokenizer's training configuration.
5. Save the learned vocabulary and merge rules.

### Example

Starting with:

`l` + `o` + `w`

A merge can produce:

`lo` + `w`

Another merge can produce:

`low`

The actual merges depend on the training data and learned merge order.

### When Does BPE Stop?

BPE training usually stops when a configured vocabulary size or merge limit is reached, or when no eligible pairs remain, depending on the implementation.

A token does not have to be a complete grammatical word. BPE learns reusable units rather than identifying complete words.

**Key Idea:** BPE repeatedly merges frequent adjacent pairs.

## 2. WordPiece

WordPiece is a subword tokenization algorithm associated with BERT.

It learns useful subword units using a statistical scoring objective rather than simply choosing the most frequent adjacent pair.

### Example

A BERT-style WordPiece tokenizer might represent:

`playing` → `play` + `##ing`

The `##` prefix indicates a continuation piece in the original BERT-style tokenizer.

### How It Works

1. Learn a vocabulary of useful subword units from training data.
2. Use a statistical objective to select vocabulary pieces.
3. During tokenization, split input words into pieces supported by the learned vocabulary.

The exact segmentation depends on the vocabulary and implementation.

**Key Idea:** WordPiece learns and uses subwords based on a statistical scoring approach.

## 3. SentencePiece

SentencePiece is a tokenizer framework that can use algorithms such as BPE and Unigram Language Model.

It can work directly on raw text without requiring a separate conventional word-tokenization step.

### Example

Input:

`I love coding`

An illustrative SentencePiece representation could be:

`▁I` + `▁love` + `▁coding`

The visible `▁` symbol commonly represents whitespace or a word boundary. The exact tokens depend on the trained tokenizer.

### Methods Supported

- **SentencePiece BPE:** Uses the BPE merging approach.
- **SentencePiece Unigram:** Learns a vocabulary using a probabilistic model and selects a likely segmentation from the available pieces.

**Key Idea:** SentencePiece is a framework that supports multiple tokenization methods and can tokenize raw text directly.

## 4. Comparison

| Feature | BPE | WordPiece | SentencePiece |
|---|---|---|---|
| Type | Tokenization algorithm | Tokenization algorithm | Tokenizer framework |
| Main approach | Merge frequent adjacent pairs | Learn subwords using statistical scoring | Supports BPE and Unigram |
| Example association | GPT-2-style tokenization | BERT | T5 and other models |
| Important detail | Learns merge rules | Uses a learned vocabulary | Can handle raw text directly |

Model associations can vary by implementation.

## 5. Key Takeaways

- BPE merges frequent adjacent units.
- WordPiece uses a different statistical approach to learn useful subwords.
- SentencePiece is a framework, not a single tokenization algorithm.
- SentencePiece supports both BPE and Unigram methods.
- Tokenization algorithms determine how text is divided before a language model processes it.

## 6. What I Learned

I learned the basic differences between BPE, WordPiece, and SentencePiece, how each approach represents text as tokens, and why a tokenizer's training method affects the final token sequence.
