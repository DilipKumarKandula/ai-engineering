# Prompt Engineering

## What is Prompt Engineering?

Prompt Engineering is the process of designing instructions, context, examples, and output formats that guide an LLM to produce reliable and useful results.

Think of it as communicating clearly with the model so it understands:

- What to do
- How to do it
- What output format to follow
- What rules to obey

---

# Why Prompt Engineering Matters

An LLM is a prediction engine.

The quality of the output depends heavily on the information and instructions provided.

Poor Prompt:

```text
Analyze this.
```

Good Prompt:

```text
Analyze the resume.

Identify:
- Strengths
- Missing Skills
- Improvement Suggestions

Return the result in JSON format.
```

The second prompt provides clear expectations and produces more reliable output.

---

# How Prompts Work

A prompt is the information sent to the model.

Modern AI applications often build prompts using:

```text
System Prompt

Memory

RAG Context

Tool Results

User Message
```

All of these are combined and sent to the LLM.

---

# System Prompt

The System Prompt defines the behavior of the model.

Think:

```text
System Prompt
=
Operating Instructions
```

Example:

```text
You are a professional resume assistant.

Use provided context only.

Never invent experience.

Answer professionally.
```

The system prompt influences how the model behaves regardless of the user question.

---

# Prompt Hierarchy

A typical hierarchy looks like:

```text
System Prompt
      ↓

Developer Instructions
      ↓

User Message
```

Higher-level instructions generally have higher priority.

---

# Few-Shot Prompting

Few-Shot Prompting teaches the model using examples.

Instead of only giving instructions, examples demonstrate the expected pattern.

Example:

```text
Input:
React, Next.js, Node.js

Output:
["React", "Next.js", "Node.js"]

Input:
Java, Spring Boot, MySQL

Output:
["Java", "Spring Boot", "MySQL"]
```

The model learns the desired output structure from the examples.

---

# Types of Prompting

## Zero-Shot

Only instructions.

```text
Extract skills from the resume.
```

---

## One-Shot

One example is provided.

```text
Example
+
Task
```

---

## Few-Shot

Multiple examples are provided.

```text
Example 1
Example 2
Example 3
+
Task
```

---

# Structured Outputs

AI applications often need structured data instead of paragraphs.

Bad:

```text
The candidate knows React and Node.js.
```

Good:

```json
{
  "skills": ["React", "Node.js"]
}
```

Structured outputs are easier for software systems to process.

---

# Why Structured Outputs Matter

Applications frequently need:

```text
JSON

Objects

Schemas

Function Arguments
```

rather than free-form text.

Structured outputs improve:

- Reliability
- Parsing
- Automation
- Integration

---

# Chain of Thought (CoT)

Chain of Thought encourages step-by-step reasoning.

Instead of:

```text
Question
 ↓
Answer
```

The model follows:

```text
Question
 ↓
Reasoning
 ↓
Answer
```

Example:

```text
Requirements:
React
Node.js
TypeScript

Resume:
React
Node.js

Reasoning:
Match React
Match Node.js
Missing TypeScript

Conclusion:
Partially Qualified
```

This improves reasoning quality and transparency.

---

# Prompt Templates

Prompt templates create reusable prompt structures.

Template:

```text
You are a resume assistant.

Resume:
{resume}

Job Description:
{job}

Task:
Compare the resume and job description.
```

Variables are inserted dynamically.

Benefits:

- Reusability
- Consistency
- Easier Maintenance

---

# Agent Prompts

Agent prompts are designed to guide autonomous behavior.

Example:

```text
You are an autonomous resume agent.

Think before acting.

Use tools when required.

Analyze tool results.

Complete the user's goal before responding.
```

Agent prompts focus on:

- Planning
- Reasoning
- Tool Usage
- Goal Completion

---

# Tool Use Instructions

Tool instructions help the model understand:

```text
When To Use Tools

When Not To Use Tools

Which Tool To Select
```

Example:

```text
Use searchJobs() only when job information is needed.

Use generatePDF() only when a PDF is requested.

Never call tools unnecessarily.
```

These instructions reduce unnecessary tool usage.

---

# Prompt Engineering Best Practices

## Be Specific

Bad:

```text
Analyze this resume.
```

Better:

```text
Analyze the resume.

Identify:
- Skills
- Strengths
- Missing Skills
```

---

## Define The Role

Example:

```text
You are a senior technical recruiter.
```

Roles provide context and perspective.

---

## Define Output Format

Example:

```json
{
  "skills": []
}
```

This improves consistency.

---

## Provide Context

More relevant context generally produces better outputs.

Example:

```text
Resume

Job Description

User Question
```

---

## Use Examples

Few-shot examples often improve output quality and formatting.

---

## Prevent Hallucinations

Example:

```text
Use only provided information.

If information is missing,
say you do not know.
```

This reduces unsupported claims.

---

## Separate Instructions From Data

Bad:

```text
Analyze React Node.js Next.js
```

Better:

```text
Task:
Analyze the resume.

Resume:
React
Node.js
Next.js
```

---

## Encourage Reasoning

Example:

```text
Analyze requirements.

Identify gaps.

Then provide recommendations.
```

---

## Test Prompts

Prompts should be evaluated just like software.

Example:

```text
Prompt
 ↓

Multiple Test Cases
 ↓

Analyze Results
 ↓

Improve Prompt
```

---

# Common Prompting Mistakes

## Vague Instructions

```text
Analyze this.
```

---

## Missing Output Format

Output becomes inconsistent.

---

## No Context

The model lacks information needed for accurate responses.

---

## No Examples

Formatting and behavior become less predictable.

---

## Hallucination Risk

Failing to instruct the model to use only available information.

---

# Production Prompt Structure

Many AI applications use:

```text
Role

Instructions

Rules

Output Format

Examples

Context

User Request
```

This structure improves reliability and maintainability.

---

# Mental Model

Think:

```text
Prompt Engineering
=
Clear Instructions
+
Good Context
+
Useful Examples
+
Reliable Output Structure
```

Prompt Engineering is not about finding magical phrases.

It is about designing prompts that consistently guide the model toward the desired behavior.

---

# Key Takeaways

- Prompts define how the model behaves.
- System prompts provide high-level instructions.
- Few-shot prompting teaches through examples.
- Structured outputs improve automation.
- Chain of Thought improves reasoning.
- Prompt templates improve reuse and consistency.
- Agent prompts guide autonomous workflows.
- Tool instructions control tool usage.
- Best practices improve reliability and reduce hallucinations.
- Prompts should be tested and evaluated like software.
