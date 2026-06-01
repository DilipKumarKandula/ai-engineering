# 07 - AI Systems

## Introduction

Many people use these terms interchangeably:

```text
LLM
AI Application
RAG Application
AI Agent
```

However, they represent different levels of AI systems.

Understanding the difference is important because most modern AI products are built by combining these concepts.

---

# Level 1 - LLM

## What is an LLM?

An LLM (Large Language Model) is a model trained to understand and generate human language.

Examples:

- GPT
- Gemini
- Claude
- Llama

---

## LLM Architecture

```text
User Question
      ↓
LLM
      ↓
Answer
```

Example:

Input:

```text
What is React?
```

Output:

```text
React is a JavaScript library used for building user interfaces.
```

---

## Characteristics

- Generates text
- Understands language
- Has no direct access to your documents
- Has no tools by default
- Has no long-term memory by default

---

# Level 2 - AI Application

## What is an AI Application?

An AI Application is software built around an LLM.

The application provides:

- User Interface
- Backend Logic
- Authentication
- Data Storage
- LLM Integration

---

## AI Application Architecture

```text
User
 ↓
Frontend
 ↓
Backend
 ↓
LLM
 ↓
Response
```

---

## Example

LinkedIn Post Generator:

```text
User Topic
      ↓
Backend
      ↓
LLM
      ↓
Generated Post
```

---

## Characteristics

- Uses an LLM
- Adds product features
- Includes business logic
- Includes UI and backend

---

# Level 3 - RAG Application

## What is a RAG Application?

A RAG Application extends an AI Application by allowing access to external knowledge.

RAG stands for:

```text
Retrieval
Augmented
Generation
```

---

## Why RAG Exists

An LLM only knows what it learned during training.

It does not automatically know:

- Your resume
- Company documents
- Uploaded PDFs
- Internal knowledge bases

RAG solves this problem.

---

## RAG Architecture

```text
User Question
      ↓
Embedding
      ↓
Vector Search
      ↓
Relevant Context
      ↓
LLM
      ↓
Answer
```

---

## Example

User asks:

```text
Do I have frontend experience?
```

Resume contains:

```text
Built LMS using React.
```

The system retrieves the relevant section and sends it to the LLM.

The LLM generates the final answer.

---

## Characteristics

- Uses embeddings
- Uses vector databases
- Uses retrieval
- Allows AI to answer questions about external data

---

# Level 4 - AI Agent

## What is an AI Agent?

An AI Agent is a system that can:

- Reason
- Plan
- Choose tools
- Perform actions
- Complete multi-step tasks

Instead of immediately answering, it decides what should happen next.

---

## Agent Architecture

```text
User Request
      ↓
Agent
      ↓
Reason
      ↓
Use Tools
      ↓
Collect Results
      ↓
Answer
```

---

## Example

User says:

```text
Find React jobs and create a tailored resume.
```

Agent workflow:

```text
1. Read Resume
2. Search Jobs
3. Compare Skills
4. Rewrite Resume
5. Generate PDF
6. Return Result
```

The system performs multiple actions before generating the answer.

---

## Characteristics

- Uses tools
- Uses reasoning
- Uses planning
- Can execute multi-step workflows

---

# Comparing All Four Levels

## LLM

```text
Question
 ↓
LLM
 ↓
Answer
```

Focus:

```text
Text Generation
```

---

## AI Application

```text
User
 ↓
App
 ↓
LLM
 ↓
Response
```

Focus:

```text
Product Experience
```

---

## RAG Application

```text
Question
 ↓
Embedding
 ↓
Vector Search
 ↓
Context
 ↓
LLM
 ↓
Answer
```

Focus:

```text
External Knowledge
```

---

## AI Agent

```text
Request
 ↓
Reason
 ↓
Tool Usage
 ↓
Actions
 ↓
Answer
```

Focus:

```text
Task Completion
```

---

# Real World Examples

## LLM

Example:

```text
What is JavaScript?
```

↓

```text
Generated Answer
```

---

## AI Application

Example:

```text
LinkedIn Post Generator
```

Uses:

```text
Frontend
+
Backend
+
LLM
```

---

## RAG Application

Example:

```text
Chat with PDF
```

Uses:

```text
Embeddings
+
Vector Database
+
LLM
```

---

## AI Agent

Example:

```text
Resume Agent
```

Uses:

```text
LLM
+
Tools
+
Planning
+
Workflows
```

---

# Evolution of AI Systems

```text
LLM
 ↓
AI Application
 ↓
RAG Application
 ↓
AI Agent
```

Each level builds on top of the previous one.

---

# Important Understanding

Many products marketed as:

```text
AI Agent
```

are actually:

```text
AI Applications
```

because they only send prompts to an LLM and return responses.

A true agent usually:

- Uses tools
- Makes decisions
- Executes actions
- Handles multiple steps

---

# Key Takeaways

- An LLM generates language.
- An AI Application wraps an LLM inside a product.
- A RAG Application adds external knowledge retrieval.
- An AI Agent adds planning, reasoning, and tool usage.
- Most modern AI products are combinations of these components.
- Understanding the difference helps design better AI systems.
