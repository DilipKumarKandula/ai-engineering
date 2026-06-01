# 05 - Vector Databases

## What is a Vector Database?

A vector database is a database designed to store and search embeddings (vectors).

Traditional databases search using exact values.

Vector databases search using meaning and similarity.

---

## Why Do We Need Vector Databases?

Suppose we have a document:

```text id="n7djg8"
React helps create web user interfaces.
```

A user searches:

```text id="j2vp0m"
How do I build user interfaces?
```

The words do not match exactly.

Traditional search may miss the document.

However, the meanings are similar.

This is where vector databases help.

---

## Traditional Database vs Vector Database

### Traditional Database

Stores:

```text id="i2j89a"
ID
Name
Email
Age
```

Example:

| ID  | Name  |
| --- | ----- |
| 1   | Dilip |
| 2   | John  |

Search:

```sql id="5m3pqw"
SELECT *
FROM users
WHERE name = 'Dilip';
```

Search is based on exact matching.

---

### Vector Database

Stores:

```text id="9wwmzm"
Vector
+
Original Text
```

Example:

```text id="5vzc2n"
Vector:
[0.82, 0.31, 0.91]

Text:
React helps create web user interfaces.
```

Search is based on similarity.

---

## What Gets Stored?

When processing a document:

```text id="bhq1c3"
Document
 ↓
Embedding Model
 ↓
Vector
```

The database stores:

```text id="97dz1o"
Vector
+
Original Text
```

Example:

```text id="yk4q1d"
Vector:
[0.82, 0.31, 0.91]

Text:
React helps create web user interfaces.
```

Both are important.

---

## Why Store the Original Text?

Vectors are useful for searching.

But vectors alone cannot answer questions.

Example:

```text id="szt5vl"
[0.82, 0.31, 0.91]
```

does not tell GPT anything useful.

The original text is required.

Example:

```text id="6x0m2g"
React helps create web user interfaces.
```

This is the information that will later be sent to the LLM.

---

## Semantic Search

Semantic Search means searching by meaning instead of exact keywords.

Example:

Document:

```text id="jwbl9z"
React helps create web UIs.
```

User asks:

```text id="4j5a3r"
How do I build user interfaces?
```

Keyword search:

```text id="b8xq9n"
user interfaces
≠
web UIs
```

May fail.

---

Semantic search:

```text id="vy9f4v"
user interfaces
≈
web UIs
```

Understands the similarity of meaning.

---

## Vector Search Flow

### Step 1

Store documents.

```text id="g5v90m"
Document
 ↓
Embedding Model
 ↓
Vector
 ↓
Vector Database
```

---

### Step 2

User asks a question.

```text id="m87k4f"
Question
 ↓
Embedding Model
 ↓
Question Vector
```

---

### Step 3

Compare vectors.

```text id="pf9g0j"
Question Vector
 ↓
Compare
 ↓
Stored Vectors
```

---

### Step 4

Find the closest matches.

```text id="d7xl8u"
Most Similar Vectors
 ↓
Original Text
```

---

### Step 5

Return the relevant text.

```text id="9wvh6t"
Relevant Chunks
```

These chunks can then be sent to an LLM.

---

## Real Example

Stored Resume Chunk:

```text id="7t1n2z"
Built LMS using React.
```

Stored Vector:

```text id="8v53jl"
[0.81, 0.30, 0.92]
```

---

User asks:

```text id="f2yxqg"
Do I have frontend experience?
```

Question becomes:

```text id="1xjk95"
[0.82, 0.31, 0.91]
```

The vectors are similar.

The vector database returns:

```text id="ec2qlx"
Built LMS using React.
```

This can now be used by an LLM.

---

## Similarity Search

The database searches for vectors that are closest together.

Example:

```text id="0gtxg7"
Question Vector

      ↓

Stored Vector A  ← Very Close
Stored Vector B
Stored Vector C
```

The closest vectors are considered most relevant.

---

## Common Vector Databases

Popular vector databases include:

- Pinecone
- Weaviate
- Qdrant
- Chroma

All of them are designed to store and search embeddings efficiently.

---

## Traditional Search vs Semantic Search

### Traditional Search

```text id="m7dyl2"
Search By Words
```

Example:

```text id="e1g6xn"
React
```

must appear exactly.

---

### Semantic Search

```text id="1gtv38"
Search By Meaning
```

Example:

```text id="8cc4r4"
frontend development
```

can still match:

```text id="ikj4lr"
React development
```

because the meanings are related.

---

## Role in Modern AI Systems

Vector databases are a core part of modern AI applications.

They enable:

- Chat with PDFs
- Knowledge Bases
- Resume Analysis
- Semantic Search
- AI Assistants
- RAG Systems

Without vector databases, large document retrieval would be inefficient.

---

## Key Takeaways

- A vector database stores embeddings and their related text.
- Vector databases search using similarity rather than exact keywords.
- Semantic search focuses on meaning.
- Original text must be stored along with vectors.
- Vectors help find information; text provides the actual knowledge.
- Vector databases are a foundation of RAG systems.
- Modern AI applications frequently use vector databases to retrieve relevant information.
