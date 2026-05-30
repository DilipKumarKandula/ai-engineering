# 06 - RAG (Retrieval Augmented Generation)

## What is RAG?

RAG stands for:

```text id="vq2i95"
Retrieval
Augmented
Generation
```

RAG is a technique that allows an LLM to answer questions using external data that was not part of its training.

---

## Why Do We Need RAG?

Suppose GPT finished training in 2025.

Now you upload a new resume today.

Example:

```text id="3r3qot"
Resume.pdf
```

GPT was never trained on your resume.

Without RAG:

```text id="2c7p7e"
Question:
What frontend technologies are listed in my resume?

↓

GPT:
I don't know.
```

Because the resume was never part of training.

---

## The Problem

LLMs have limited knowledge.

They only know:

```text id="hk2mkt"
Training Data
```

They do not automatically know:

```text id="7zzy9i"
Your Resume
Company Documents
Private PDFs
Internal Knowledge Bases
```

We need a way to provide that information.

---

## What RAG Does

RAG retrieves relevant information and provides it to the LLM before generating a response.

Process:

```text id="r7zq1n"
Question
 ↓
Retrieve Relevant Data
 ↓
Add Context
 ↓
LLM
 ↓
Answer
```

---

## Full RAG Architecture

```text id="j43n6k"
User Question
      ↓
Embedding
      ↓
Vector Search
      ↓
Relevant Text
      ↓
LLM
      ↓
Answer
```

This is the core architecture behind many modern AI applications.

---

## Understanding the Name

### Retrieval

Find relevant information.

Example:

```text id="tbqhhj"
Resume Chunks
```

stored inside a vector database.

Retrieve the most relevant ones.

---

### Augmented

Add the retrieved information to the prompt.

Example:

```text id="gprzz3"
Question
+
Relevant Resume Sections
```

---

### Generation

The LLM generates the final answer.

---

## The Two Phases of RAG

RAG has two major phases:

### Indexing Phase

Happens when documents are uploaded.

### Retrieval Phase

Happens when users ask questions.

---

# Phase 1: Indexing

## Step 1 - Upload Document

Example:

```text id="6gn4v5"
Resume.pdf
```

---

## Step 2 - Extract Text

Example:

```text id="xjwttv"
Built LMS using React.

Developed APIs using Node.js.
```

---

## Step 3 - Split into Chunks

Example:

Chunk 1:

```text id="h75xnl"
Built LMS using React.
```

Chunk 2:

```text id="g7npod"
Developed APIs using Node.js.
```

---

## Step 4 - Generate Embeddings

```text id="c5q7n6"
Chunk
 ↓
Embedding Model
 ↓
Vector
```

Example:

```text id="i6n26i"
[0.81, 0.30, 0.92]
```

---

## Step 5 - Store in Vector Database

Store:

```text id="7s58y3"
Vector
+
Original Text
```

The indexing phase is now complete.

---

## Indexing Flow

```text id="2klqri"
PDF
 ↓
Extract Text
 ↓
Split Into Chunks
 ↓
Create Embeddings
 ↓
Store In Vector Database
```

---

# Phase 2: Retrieval

This happens when the user asks a question.

---

## Step 1 - User Question

Example:

```text id="ak5gxj"
Do I have frontend experience?
```

---

## Step 2 - Create Question Embedding

```text id="x3lt9y"
Question
 ↓
Embedding
 ↓
Vector
```

---

## Step 3 - Vector Search

Search for similar vectors.

```text id="mj3r4j"
Question Vector
 ↓
Compare
 ↓
Stored Vectors
```

---

## Step 4 - Retrieve Relevant Chunks

Example:

```text id="v6v6g0"
Built LMS using React.
```

This chunk is semantically related to frontend development.

---

## Step 5 - Build Prompt

The application creates a prompt.

Example:

```text id="n8w58o"
Question:
Do I have frontend experience?

Context:
Built LMS using React.
```

---

## Step 6 - Send to LLM

The prompt is sent to the LLM.

---

## Step 7 - Generate Answer

Example:

```text id="tx4p7t"
Yes.

You have frontend experience because
you built an LMS using React.
```

---

## Retrieval Flow

```text id="vtnd3u"
User Question
 ↓
Embedding
 ↓
Vector Search
 ↓
Relevant Chunks
 ↓
Build Prompt
 ↓
LLM
 ↓
Answer
```

---

## Important Understanding

The vector database does not answer questions.

Its job is:

```text id="3nrfyk"
Find Relevant Information
```

The LLM does not search documents.

Its job is:

```text id="0y8z7s"
Generate Responses
```

Together:

```text id="r90lk2"
Vector Database
+
LLM
=
RAG System
```

---

## RAG Example

Resume contains:

```text id="2ljw2k"
Built LMS using React.
```

User asks:

```text id="yb2i7k"
Do I have frontend experience?
```

Vector Search retrieves:

```text id="tch3bc"
Built LMS using React.
```

Prompt becomes:

```text id="4v5kmi"
Question:
Do I have frontend experience?

Context:
Built LMS using React.
```

LLM generates:

```text id="eq4h2e"
Yes, you have frontend experience.
```

---

## Common RAG Applications

- Chat with PDFs
- Resume Analysis
- Company Knowledge Bases
- Internal Documentation Search
- Customer Support Systems
- AI Assistants
- Research Assistants

---

## Why RAG is Important

Without RAG:

```text id="dr3d7w"
LLM
 ↓
Training Knowledge Only
```

With RAG:

```text id="nwd8om"
LLM
 +
Your Documents
 +
Your Data
 +
Latest Information
```

This makes AI systems much more useful in real-world applications.

---

## Key Takeaways

- RAG stands for Retrieval Augmented Generation.
- RAG allows LLMs to use information outside their training data.
- RAG has two phases: Indexing and Retrieval.
- Documents are converted into embeddings and stored in a vector database.
- User questions are converted into embeddings for similarity search.
- Retrieved text is added to the prompt before calling the LLM.
- Vector databases retrieve information.
- LLMs generate answers.
- Most modern AI applications use RAG in some form.
