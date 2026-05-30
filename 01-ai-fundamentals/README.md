# 01 - AI Fundamentals

## What is AI?

AI (Artificial Intelligence) is a system that performs tasks that normally require human intelligence.

Examples:

- Answering questions
- Writing content
- Understanding images
- Recognizing speech
- Making recommendations
- Translating languages

---

## AI vs Traditional Software

### Traditional Software

Traditional software follows rules written by developers.

Example:

```js
if (marks > 35) {
  return "Pass";
} else {
  return "Fail";
}
```

The developer defines all the rules.

---

### AI Software

AI learns patterns from data instead of relying only on manually written rules.

Example:

Input:

```text
What is React?
```

Output:

```text
React is a JavaScript library used for building user interfaces.
```

The answer is generated from learned patterns.

---

## The Core Idea of Modern AI

Most modern AI systems work through prediction.

Very simplified:

```text
Input
 ↓
Predict Next Part
 ↓
Generate Output
```

Example:

Input:

```text
What is Node.js?
```

AI predicts:

```text
Node.js
```

Then predicts:

```text
is
```

Then predicts:

```text
a
```

Then predicts:

```text
JavaScript
```

And continues until a complete answer is generated.

---

## Types of AI

There are multiple ways to classify AI.

### 1. By Intelligence Level

#### ANI (Artificial Narrow Intelligence)

AI designed for specific tasks.

Examples:

- ChatGPT
- Gemini
- Recommendation Systems
- Self-Driving Features

Current AI systems belong to this category.

---

#### AGI (Artificial General Intelligence)

A hypothetical AI system that can perform any intellectual task a human can perform.

Characteristics:

- Learns new tasks
- Adapts to different domains
- General problem solving

AGI does not currently exist.

---

#### ASI (Artificial Super Intelligence)

A hypothetical AI system that surpasses human intelligence in most or all areas.

ASI does not currently exist.

---

### 2. By Capability / Modality

#### Text AI

Input:

```text
Write a LinkedIn post about React.
```

Output:

```text
Generated content
```

Examples:

- ChatGPT
- Gemini
- Claude

---

#### Image AI

Input:

```text
Cat riding a bicycle
```

Output:

```text
Generated image
```

Examples:

- DALL-E
- Midjourney

---

#### Speech AI

Input:

```text
Audio
```

Output:

```text
Text
```

Example:

Speech-to-Text systems.

---

#### Voice AI

Input:

```text
Text
```

Output:

```text
Speech
```

Example:

Text-to-Speech systems.

---

#### Vision AI

Input:

```text
Image
```

Output:

```text
Description or Analysis
```

Example:

Image recognition systems.

---

#### Video AI

Input:

```text
Prompt or Video
```

Output:

```text
Generated or Processed Video
```

Examples:

- Video Generation Models
- Video Analysis Systems

---

## Important Understanding

Many AI products do not create their own AI models.

Instead:

```text
Frontend
 ↓
Backend
 ↓
Existing AI Model
 ↓
Result
```

The value often comes from:

- Workflow
- User Experience
- Automation
- Data
- Business Logic

rather than training a new model.

---

## Key Takeaways

- AI performs tasks that normally require human intelligence.
- Modern AI systems primarily learn patterns from data.
- Most modern AI works through prediction.
- AI can be classified by intelligence level (ANI, AGI, ASI).
- AI can also be classified by capability (Text, Image, Speech, Vision, Video).
- Most AI products today are built on top of existing AI models rather than training new ones.
