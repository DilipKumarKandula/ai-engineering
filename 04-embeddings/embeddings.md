# 04 - Embeddings

## What are Embeddings?

An embedding is a numerical representation of meaning.

Computers cannot understand text directly. They work with numbers.

Example:

```text
React
```

might be represented as:

```text
[0.82, 0.31, 0.91, ...]
```

The numbers above are only examples.

The purpose of an embedding is to capture the meaning of text in a numerical format.

---

## Why Embeddings Exist

Computers do not understand:

```text
React
Angular
Dog
Cat
```

directly.

They need numerical representations.

Process:

```text
Text
 ↓
Embedding Model
 ↓
Vector
```

The vector captures the meaning of the text.

---

## Text to Vectors

Example:

```text
React
```

↓

```text
[0.82, 0.31, 0.91, ...]
```

---

Example:

```text
Angular
```

↓

```text
[0.80, 0.29, 0.88, ...]
```

---

Example:

```text
Dog
```

↓

```text
[0.12, 0.93, 0.24, ...]
```

The actual vectors contain many more dimensions.

The numbers shown here are simplified examples.

---

## Meaning as Numbers

Embeddings allow machines to represent meaning mathematically.

Instead of storing:

```text
React
```

the system can store:

```text
Vector Representation
```

This allows mathematical comparison between concepts.

---

## Semantic Similarity

Similar concepts should have similar embeddings.

Example:

```text
React
Angular
Vue
```

These technologies are related.

Their embeddings should be close together.

---

Similarly:

```text
Dog
Cat
Tiger
```

These concepts are related.

Their embeddings should also be close together.

---

Different concepts should be further apart.

Example:

```text
React
```

and

```text
Tiger
```

should not be close because their meanings are unrelated.

---

## Visual Representation

Imagine a map of meanings:

```text
Frontend Technologies

React      Angular      Vue



Animals

Dog         Cat         Tiger
```

Similar concepts form clusters.

Embeddings help machines understand these relationships.

---

## Context Matters

The same word can have different meanings.

Example:

```text
I sat on the bank of the river.
```

---

Example:

```text
I deposited money in the bank.
```

The word:

```text
bank
```

appears in both sentences.

However, the meaning is different.

Modern embedding models use context to capture the correct meaning.

---

## Embeddings vs Traditional IDs

A normal database ID might look like:

```text
React = 1
Angular = 2
Vue = 3
Dog = 4
```

These numbers contain no meaning.

---

Embeddings are different:

```text
React
=
[0.82, 0.31, 0.91]

Angular
=
[0.80, 0.29, 0.88]
```

Because the vectors are similar, the system can understand that React and Angular are related.

---

## Embeddings vs Weights

Many beginners confuse embeddings and weights.

### Weights

Weights are learned numerical values inside a neural network.

They influence predictions.

Example:

```text
Training
 ↓
Weight Adjustment
 ↓
Better Predictions
```

Weights help the model learn patterns.

---

### Embeddings

Embeddings represent meaning as vectors.

Example:

```text
Text
 ↓
Embedding
 ↓
Vector
```

Embeddings help systems compare meaning.

---

### Quick Comparison

| Weights                 | Embeddings                 |
| ----------------------- | -------------------------- |
| Learned during training | Generated from text        |
| Influence predictions   | Represent meaning          |
| Exist inside the model  | Can be stored externally   |
| Used for learning       | Used for similarity search |

---

## Real World Example

User asks:

```text
How do I build user interfaces?
```

Document contains:

```text
React helps create web UIs.
```

Traditional keyword search may miss this.

Why?

Because:

```text
user interfaces
```

and

```text
web UIs
```

are different words.

---

Embedding search understands that:

```text
user interfaces
```

and

```text
web UIs
```

have similar meanings.

This allows more intelligent search.

---

## Why Embeddings Matter

Embeddings are used in:

- Semantic Search
- Vector Databases
- RAG Systems
- Resume Matching
- Recommendation Systems
- Chat with PDFs
- Knowledge Bases
- AI Assistants

Most modern AI applications use embeddings in some form.

---

## Embeddings in AI Applications

Example:

```text
Resume
 ↓
Embedding
 ↓
Vector
 ↓
Store
```

Later:

```text
Question
 ↓
Embedding
 ↓
Similarity Search
 ↓
Relevant Resume Sections
```

This allows AI systems to retrieve useful information based on meaning rather than exact keywords.

---

## Key Takeaways

- Embeddings are numerical representations of meaning.
- Computers use embeddings to understand relationships between concepts.
- Similar concepts have similar embeddings.
- Different concepts have embeddings that are further apart.
- Context affects meaning and therefore affects embeddings.
- Embeddings are different from weights.
- Embeddings power semantic search, vector databases, and RAG systems.
- Most modern AI applications rely on embeddings to retrieve relevant information.
