# 10 - Agent Workflows

## Introduction

Tool Calling allows an LLM to use tools.

However, using a single tool does not automatically make a system an AI Agent.

An AI Agent is a system that can:

- Understand a goal
- Create a plan
- Choose tools
- Execute actions
- Observe results
- Decide next steps
- Continue until the goal is achieved

---

## What is an Agent Workflow?

An Agent Workflow is the sequence of decisions and actions an agent performs to achieve a goal.

Simple workflow:

```text
Goal
 ↓
Plan
 ↓
Action
 ↓
Observe
 ↓
Next Action
 ↓
Goal Achieved
```

---

## Tool Calling vs Agent Workflow

### Tool Calling

```text
User Request
 ↓
Choose Tool
 ↓
Execute Tool
 ↓
Return Result
```

One decision.

---

### Agent Workflow

```text
Goal
 ↓
Reason
 ↓
Choose Tool
 ↓
Observe Result
 ↓
Reason Again
 ↓
Choose Next Tool
 ↓
Goal Achieved
```

Multiple decisions.

---

## Why Agent Workflows Exist

Many tasks require multiple steps.

Example:

```text
Create a tailored resume for React jobs.
```

One tool cannot complete the task.

The agent must:

```text
Read Resume
 ↓
Search Jobs
 ↓
Analyze Skills
 ↓
Update Resume
 ↓
Generate PDF
```

This sequence is called a workflow.

---

# Planning

## What is Planning?

Planning is the process of deciding the steps required to achieve a goal.

Example:

User:

```text
Find React jobs and create a tailored resume.
```

Agent creates a plan:

```text
1. Read Resume
2. Search Jobs
3. Compare Skills
4. Improve Resume
5. Generate PDF
```

The plan is created before actions begin.

---

## Why Planning Matters

Without planning:

```text
Random Actions
```

With planning:

```text
Goal
 ↓
Structured Steps
 ↓
Execution
```

Planning improves reliability and task completion.

---

# Reasoning

## What is Reasoning?

Reasoning is the process of analyzing information and deciding what to do next.

Example:

Agent discovers:

```text
Most React jobs require TypeScript.
```

Resume does not contain:

```text
TypeScript
```

Reasoning:

```text
Suggest learning TypeScript
and highlight transferable skills.
```

The agent makes a decision based on available information.

---

## Reasoning Flow

```text
Information
 ↓
Analysis
 ↓
Decision
 ↓
Action
```

---

# Observation

## What is Observation?

Observation means reviewing the results returned by tools.

Example:

Tool:

```text
searchJobs()
```

Result:

```text
No jobs found.
```

The agent observes this outcome.

---

Observation allows the agent to determine what should happen next.

Example:

```text
No Jobs Found
 ↓
Try Different Search
```

---

# Agent Loop

The Agent Loop is the core behavior of most AI agents.

```text
Goal
 ↓
Think
 ↓
Plan
 ↓
Use Tool
 ↓
Observe
 ↓
Think Again
 ↓
Use Next Tool
 ↓
Goal Achieved
```

This cycle continues until the objective is completed.

---

## Why the Agent Loop Matters

Unlike traditional software:

```text
Step 1
 ↓
Step 2
 ↓
Step 3
```

An agent can adapt.

Example:

```text
Search Flights
 ↓
No Results
 ↓
Search Trains
```

The workflow changes based on observations.

---

# Multi-Step Execution

Most real-world tasks require multiple actions.

Example:

User:

```text
Create a tailored resume for React jobs.
```

Possible execution:

```text
readResume()
 ↓

searchJobs()
 ↓

compareSkills()
 ↓

generateResume()
 ↓

generatePDF()
```

Each step depends on the results of previous steps.

---

# Agent Architecture

```text
User Goal
      ↓

     Agent

      ↓

 Planning

      ↓

 Reasoning

      ↓

 Tool Usage

      ↓

 Observation

      ↓

 Final Response
```

---

# Example: Resume Agent

## User Goal

```text
Create a tailored resume for React jobs.
```

---

## Plan

```text
1. Read Resume
2. Find React Jobs
3. Compare Requirements
4. Improve Resume
5. Generate PDF
```

---

## Execution

```text
readResume()
 ↓

searchJobs()
 ↓

compareSkills()
 ↓

generatePDF()
```

---

## Result

```text
Tailored Resume Generated
```

Goal achieved.

---

# Workflow vs Agent

### Traditional Workflow

```text
Fixed Steps
```

Example:

```text
Upload File
 ↓
Process File
 ↓
Generate Report
```

Always follows the same path.

---

### Agent Workflow

```text
Goal
 ↓
Reason
 ↓
Adapt
 ↓
Take Action
```

The path can change depending on results.

---

# Agent Mental Model

Think of:

```text
Tools
      = Hands

Memory
      = Memory

RAG
      = Knowledge

Planning
      = Strategy

Reasoning
      = Decision Making

LLM
      = Brain
```

Together they form an AI Agent.

---

# Characteristics of an AI Agent

A true AI Agent typically has:

- Goal Understanding
- Planning
- Reasoning
- Tool Usage
- Observation
- Memory
- Adaptability

---

# Real World Agent Examples

### Resume Agent

```text
Analyze Resume
 ↓
Find Jobs
 ↓
Generate Tailored Resume
```

---

### Travel Agent

```text
Search Flights
 ↓
Search Hotels
 ↓
Create Itinerary
```

---

### Email Agent

```text
Read Email
 ↓
Classify Email
 ↓
Draft Reply
 ↓
Send Reply
```

---

### Automation Agent

```text
Monitor Event
 ↓
Process Data
 ↓
Store Information
 ↓
Notify User
```

---

# Key Takeaways

- An Agent Workflow is the process used to achieve a goal.
- Planning determines what steps are required.
- Reasoning determines what should happen next.
- Observation evaluates the results of actions.
- Agent workflows are dynamic and adaptive.
- Most agents operate using a continuous loop of planning, action, and observation.
- Tool Calling enables actions; Agent Workflows enable goal completion.
- Planning and reasoning are what transform a tool-calling system into an AI Agent.
