# 08 - Memory

## Introduction

Memory allows an AI system to remember information and use it in future interactions.

Without memory, every conversation starts from scratch.

With memory, an AI system can personalize responses and maintain context over time.

---

# Why Memory is Needed

Imagine the following conversation:

User:

```text id="1h1gk4"
My name is Dilip.
```

AI:

```text id="f6xy0u"
Nice to meet you.
```

Later:

User:

```text id="l7owb8"
What is my name?
```

Without memory:

```text id="7d9t9f"
I don't know.
```

The information is lost.

---

With memory:

```text id="f5r4du"
Your name is Dilip.
```

The system remembers previous information.

---

# What is Memory?

Memory is stored information that can be retrieved and added to future prompts.

Memory is usually stored outside the LLM.

Architecture:

```text id="aqp20e"
User Information
       ↓
Memory Store
       ↓
Retrieve
       ↓
Add To Prompt
       ↓
LLM
       ↓
Response
```

---

# Important Understanding

Many people think:

```text id="a4k5x8"
GPT remembers everything.
```

This is not usually how production systems work.

Most systems store memory in:

- Databases
- Vector Databases
- Memory Stores

The memory is later retrieved and added to the prompt.

---

# Types of Memory

## 1. Short-Term Memory

Short-term memory refers to the current conversation context.

Example:

```text id="x0m2kh"
Message 1
Message 2
Message 3
Message 4
```

The model can use previous messages in the same conversation.

---

### Example

User:

```text id="93qh2u"
I am learning React.
```

Later:

```text id="yrdb6q"
Suggest a project.
```

The AI understands:

```text id="0vlc7x"
User is learning React.
```

because the information exists in the current conversation.

---

# 2. Long-Term Memory

Long-term memory stores information beyond a single conversation.

Example:

```text id="2k3gbm"
Name = Dilip
Role = Developer
Interest = AI Engineering
```

The information is stored in a database and can be reused later.

---

### Example

User:

```text id="v7q8ha"
I am a React Developer.
```

Store:

```text id="0kl6rf"
Role = React Developer
```

---

Three days later:

User:

```text id="ovb34x"
Suggest projects for me.
```

The memory is retrieved and provided to the LLM.

---

# How Memory Works

## Step 1

User provides information.

```text id="1v4h2m"
I am a React Developer.
```

---

## Step 2

Store information.

```text id="2jh3d1"
role = React Developer
```

---

## Step 3

User asks a future question.

```text id="91ms3o"
Suggest projects.
```

---

## Step 4

Retrieve memory.

```text id="1fd4q5"
role = React Developer
```

---

## Step 5

Build prompt.

```text id="ng5v0r"
User is a React Developer.

Suggest projects.
```

---

## Step 6

Send to LLM.

---

## Step 7

Generate personalized response.

---

# Memory Architecture

```text id="w3rv8h"
User
 ↓
Memory Store
 ↓
Retrieve Relevant Information
 ↓
Add To Prompt
 ↓
LLM
 ↓
Response
```

---

# Memory vs RAG

This is a common source of confusion.

---

## Memory

Purpose:

```text id="gx3v4i"
Remember Information About The User
```

Examples:

- Name
- Preferences
- Goals
- Skills
- Interests

---

Example:

```text id="5n6mxn"
User likes React.
```

Store and reuse later.

---

## RAG

Purpose:

```text id="8fq7zq"
Retrieve Information From Documents
```

Examples:

- PDFs
- Resumes
- Company Documentation
- Knowledge Bases

---

Example:

```text id="4h1jft"
Resume.pdf
```

Retrieve relevant sections when needed.

---

# Comparison

| Memory              | RAG                  |
| ------------------- | -------------------- |
| User Information    | Document Information |
| Preferences         | Knowledge Retrieval  |
| Personal Context    | External Context     |
| Long-Term User Data | Searchable Documents |

---

# Personalized AI

Without memory:

```text id="06ybgs"
Generic Responses
```

With memory:

```text id="0s1vzr"
Personalized Responses
```

---

Example:

Without memory:

```text id="p4h5qu"
Learn a programming language.
```

---

With memory:

```text id="z8iwl5"
Since you are a React Developer,
consider learning Node.js next.
```

The response becomes more relevant.

---

# Memory in AI Agents

Most advanced AI agents use memory.

Example:

```text id="y6g6y9"
Agent
 ├── Memory
 ├── Tools
 ├── RAG
 └── LLM
```

Memory helps the agent understand the user across multiple interactions.

---

# Real World Uses

Memory is used in:

- Personal AI Assistants
- Learning Assistants
- Resume Assistants
- Customer Support Systems
- Productivity Tools
- AI Agents

---

# Important Takeaway

Memory is usually not stored inside the LLM.

Instead:

```text id="j4z0x8"
Database
 ↓
Retrieve
 ↓
Prompt
 ↓
LLM
```

This approach is more scalable and practical.

---

# Key Takeaways

- Memory allows AI systems to remember information.
- Short-term memory exists within the current conversation.
- Long-term memory is stored outside the LLM.
- Memory is retrieved and added to prompts when needed.
- Memory and RAG solve different problems.
- Memory stores user information.
- RAG retrieves document information.
- Personalized AI systems depend heavily on memory.
- Most advanced AI assistants and agents use memory systems.
