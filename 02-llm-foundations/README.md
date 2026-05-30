# 02 - LLM Foundations

## What is a Model?

A model is the result of training on large amounts of data.

Think of it as the "brain" created after training.

```text
Training Data
      ↓
Training Process
      ↓
Model
      ↓
Input → Output
```

The model learns patterns from data and uses those patterns to generate predictions.

---

## What is an LLM?

LLM stands for Large Language Model.

An LLM is a type of AI model specifically designed to understand and generate human language.

Input:

```text
What is React?
```

Output:

```text
React is a JavaScript library used for building user interfaces.
```

Examples:

- GPT
- Gemini
- Claude
- Llama

---

## Model vs LLM

```text
AI Model
├── LLM
├── Image Model
├── Speech Model
├── Vision Model
└── Video Model
```

An LLM is one type of AI model.

Not every model is an LLM.

---

## What is ChatGPT?

Many beginners think:

```text
ChatGPT = GPT
```

This is not correct.

A better view:

```text
ChatGPT
├── GPT Model
├── Chat Interface
├── Memory
├── Tools
├── File Uploads
├── Web Access
└── Other Features
```

GPT is the language model.

ChatGPT is the product built around that model.

---

## ChatGPT vs GPT

### GPT

The language model.

Input:

```text
Question
```

Output:

```text
Answer
```

---

### ChatGPT

The complete application.

```text
User
 ↓
Chat Interface
 ↓
GPT Model
 ↓
Response
```

With additional features such as:

- Memory
- File uploads
- Tools
- Web access

---

## What are Tokens?

Computers do not understand words directly.

Before processing text, the model converts text into tokens.

Example:

```text
React is awesome
```

might become:

```text
["React", " is", " awesome"]
```

The exact tokenization depends on the model.

---

## Why Tokens Exist

The model works with numbers, not text.

Process:

```text
Text
 ↓
Tokens
 ↓
Numbers
 ↓
Model Processing
```

Tokens are the building blocks used by the model.

---

## What is Next Token Prediction?

The core idea behind modern LLMs is next-token prediction.

Given some input:

```text
React is a JavaScript
```

the model predicts the most likely next token.

Possible predictions:

```text
library     75%
framework   10%
language     5%
runtime      2%
```

The model selects one of the most likely tokens.

---

## How an Answer is Generated

Example:

Input:

```text
What is Node.js?
```

The model predicts:

```text
Node.js
```

Then:

```text
is
```

Then:

```text
a
```

Then:

```text
JavaScript
```

Then:

```text
runtime
```

This process continues until a complete response is generated.

---

## Does the Model Search the Internet?

Usually, no.

The model generates responses from patterns learned during training.

```text
Question
 ↓
Model
 ↓
Prediction
 ↓
Answer
```

The answer is generated from learned relationships rather than searching a database.

---

## How Does the Model Know Things?

The model does not store facts like a traditional database.

Traditional Database:

```json
{
  "React": "Library",
  "Node.js": "Runtime"
}
```

LLM:

```text
Patterns
 ↓
Relationships
 ↓
Predictions
```

Knowledge is encoded in learned patterns rather than explicit records.

---

## Key Takeaways

- A model is created through training.
- An LLM is a language-focused AI model.
- GPT is a model; ChatGPT is a product.
- Text is converted into tokens before processing.
- Modern LLMs work through next-token prediction.
- Models learn patterns and relationships from data.
- LLMs do not behave like traditional databases.
- Responses are generated from learned patterns rather than simple lookups.
