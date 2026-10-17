# Cosine Similarity, Semantic Search, Vector Databases, and RAG

**Learning Resource:** Phillip Lacner — LLM Fundamentals

## 1. What Is Cosine Similarity?

Cosine similarity measures how much two vectors point in the same direction.

It is commonly used to compare embedding vectors in semantic-search systems.

Its mathematical formula is:

`Cosine Similarity = (A · B) / (||A|| × ||B||)`

Where:

- `A` and `B` are two vectors.
- `A · B` is their dot product.
- `||A||` and `||B||` represent their vector lengths.

The formula divides the dot product by both vector lengths, making the score independent of vector magnitude.

### Interpreting the Score

- **Close to 1:** The vectors point in similar directions.
- **Close to 0:** The vectors are perpendicular.
- **Close to -1:** The vectors point in opposite directions.

These values describe geometric relationships between vectors. Their relationship to semantic meaning depends on the embedding model.

## 2. Cosine Similarity vs. Euclidean Distance

Cosine similarity measures the angle between two vectors, while Euclidean distance measures the straight-line distance between their endpoints.

For example:

`A = [1, 0]`

`B = [2, 0]`

Both vectors point in the same direction.

- Cosine similarity is `1`.
- Euclidean distance is `1`.

Although their lengths differ, their directions are identical.

Cosine similarity is useful for many semantic-search tasks because it compares vector direction. However, Euclidean distance is also useful, and neither metric is universally better. The appropriate metric depends on the embedding model and retrieval setup.

## 3. What Is Semantic Search?

Semantic search retrieves information based on meaning and learned relationships rather than relying only on exact keyword matches.

Example query:

`How can I sleep better?`

A document contains:

`Tips for getting better rest at night.`

The wording is different, but the topics are similar.

An embedding model converts both texts into vectors. A retrieval system can then compare those vectors and identify relevant documents.

Similarity scores are not percentages of meaning or guarantees of relevance. Useful thresholds depend on the model, data, and task.

## 4. What Is a Vector Database?

A vector database stores and retrieves embedding vectors efficiently. It may also store metadata, document IDs, and references to the original content.

A simplified workflow is:

1. Convert documents into embeddings.
2. Store the vectors and associated identifiers.
3. Convert a user's query into an embedding.
4. Search for similar vectors.
5. Retrieve the associated documents or records.

Vector databases are useful for semantic search across large collections of information.

Traditional databases such as SQL databases remain useful for structured data, exact conditions, and transactions. Applications can combine SQL queries, metadata filters, and vector search when necessary.

## 5. What Is Retrieval-Augmented Generation (RAG)?

RAG stands for Retrieval-Augmented Generation.

It combines information retrieval with an LLM's ability to generate text.

A typical RAG workflow is:

1. A user submits a question.
2. The application converts the question into an embedding.
3. The retrieval system finds relevant documents or document chunks.
4. The retrieved information is added to the LLM's prompt as context.
5. The LLM generates an answer using the question and supplied context.

The retrieved information does not automatically guarantee a correct answer, but it can help the model answer questions about external or updated information.

## 6. Example: A College Placement Chatbot

Suppose a college has placement notices containing company names, eligibility requirements, deadlines, and application instructions.

A student asks:

`What is the eligibility for this placement drive?`

The application can retrieve the relevant placement notice and provide it to the LLM as context.

The LLM then generates an answer based on that information instead of relying only on what it learned during training.

For exact questions such as which students applied before a deadline or which customers renewed a subscription last month, structured database queries and accurate records may also be necessary.

## 7. How These Concepts Connect

- **Embedding vectors:** Represent text numerically.
- **Cosine similarity:** Compares the directions of vectors.
- **Semantic search:** Uses representations of meaning to find relevant information.
- **Vector database:** Stores and retrieves vectors efficiently.
- **RAG:** Supplies retrieved information to an LLM so it can generate a context-informed answer.

## 8. Key Takeaways

- Cosine similarity is a measure of vector direction.
- Euclidean distance measures the distance between vector endpoints.
- Semantic search can find relevant content even when the wording differs.
- Vector databases support efficient retrieval of similar embeddings.
- RAG connects external information retrieval with LLM-generated answers.
- Structured queries may still be necessary for exact facts, dates, and database conditions.

## 9. What I Learned

I learned how cosine similarity compares embedding vectors and how semantic search uses embeddings to find relevant information. I also understood the roles of vector databases and RAG in building applications that retrieve external information and provide it to an LLM as context.
