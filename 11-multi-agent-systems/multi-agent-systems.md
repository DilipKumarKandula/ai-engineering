# 11 - Multi-Agent Systems

## Introduction

So far we have learned about AI Agents.

A typical AI Agent contains:

```text
LLM
+
Memory
+
Tools
+
Reasoning
+
Planning
```

For many applications, a single agent is enough.

However, some tasks become large and complex.

This is where Multi-Agent Systems are used.

---

## What is a Multi-Agent System?

A Multi-Agent System is a system where multiple AI agents work together to achieve a goal.

Instead of:

```text
One Agent
```

we have:

```text
Agent
+
Agent
+
Agent
```

working collaboratively.

---

## Why Multi-Agent Systems Exist

Imagine one person responsible for:

```text
Research
Analysis
Writing
Reviewing
Presentation Creation
```

Possible?

Yes.

Efficient?

Not always.

---

Instead, organizations use specialists:

```text
Research Team
Analysis Team
Writing Team
Review Team
```

Each focuses on a specific responsibility.

Multi-Agent Systems follow a similar idea.

---

## Single Agent vs Multi-Agent

### Single Agent

Architecture:

```text
User
 ↓
Agent
 ↓
Tools
 ↓
Response
```

Characteristics:

- Simpler
- Easier to build
- Lower cost
- Easier to debug

---

### Multi-Agent

Architecture:

```text
User
 ↓
Multiple Agents
 ↓
Response
```

Characteristics:

- Specialized responsibilities
- More flexible for complex tasks
- Higher complexity
- Higher cost

---

## Example

User:

```text
Create a detailed report about a company.
```

---

Single Agent:

```text
Research
Analyze
Write
Review
```

All performed by one agent.

---

Multi-Agent:

```text
Research Agent
 ↓

Analysis Agent
 ↓

Writer Agent
 ↓

Reviewer Agent
```

Each agent performs a specialized task.

---

# Types of Multi-Agent Architectures

## 1. Sequential Architecture

Agents work one after another.

Example:

```text
Research Agent
 ↓

Analysis Agent
 ↓

Writer Agent
 ↓

Reviewer Agent
```

Output from one agent becomes input for the next.

---

### Example Workflow

```text
Research
 ↓

Analysis
 ↓

Draft Creation
 ↓

Review
 ↓

Final Output
```

---

## 2. Coordinator Architecture

A central agent manages all other agents.

Architecture:

```text
Coordinator Agent
        ↓

Research Agent

Analysis Agent

Writer Agent
```

The coordinator assigns tasks and combines results.

---

### Example

User:

```text
Analyze Tesla and create a report.
```

Coordinator:

```text
Research Agent → Gather Information

Analysis Agent → Analyze Data

Writer Agent → Create Report
```

The coordinator combines everything into a final response.

---

## 3. Parallel Architecture

Multiple agents work simultaneously.

Architecture:

```text
Agent A

Agent B

Agent C
```

running at the same time.

---

Example:

```text
Research Competitors

Research Market

Research Customers
```

All agents operate concurrently.

---

Benefits:

- Faster execution
- Better scalability

---

# Agent Communication

Agents must exchange information.

Example:

```text
Research Agent
 ↓

Research Results
 ↓

Writer Agent
```

The writer cannot create content without research data.

Communication is essential.

---

## Communication Flow

```text
Agent A
 ↓

Result
 ↓

Agent B
 ↓

Result
 ↓

Agent C
```

Agents pass information through messages or shared memory.

---

# Shared Memory

Some Multi-Agent Systems use shared memory.

Architecture:

```text
Agent A
      ↓

Shared Memory

      ↑
Agent B
```

---

Example:

```text
Research Results
```

stored in memory.

Multiple agents can access the same information.

---

# Specialized Agents

Each agent can focus on a specific responsibility.

Example:

### Research Agent

Responsible for:

```text
Data Collection
```

---

### Analysis Agent

Responsible for:

```text
Data Analysis
```

---

### Writer Agent

Responsible for:

```text
Content Creation
```

---

### Reviewer Agent

Responsible for:

```text
Quality Checks
```

---

Specialization can improve performance for complex workflows.

---

# Real World Example

## Content Generation System

User:

```text
Create a blog about React.
```

Workflow:

```text
Research Agent
 ↓

Writer Agent
 ↓

Reviewer Agent
 ↓

Final Blog
```

---

## Travel Planning System

User:

```text
Plan a trip to Bangalore.
```

Workflow:

```text
Flight Agent
 ↓

Hotel Agent
 ↓

Itinerary Agent
 ↓

Final Plan
```

---

## Business Research System

User:

```text
Analyze a company.
```

Workflow:

```text
Research Agent
 ↓

Financial Agent
 ↓

Strategy Agent
 ↓

Report Agent
```

---

# Advantages of Multi-Agent Systems

- Task specialization
- Better scalability
- Separation of responsibilities
- Easier management of complex workflows
- Ability to parallelize work

---

# Challenges of Multi-Agent Systems

- More complexity
- More LLM calls
- Higher cost
- Harder debugging
- Agent coordination challenges
- Communication overhead

---

# Important Industry Reality

Many applications do not require multiple agents.

Example:

```text
Resume Agent
```

can usually be implemented as:

```text
One Agent
+
Multiple Tools
```

without introducing unnecessary complexity.

---

# When to Use a Single Agent

Use a single agent when:

- Tasks are straightforward
- Workflow is relatively simple
- Cost is important
- Development speed matters

Examples:

- Resume Agent
- Email Agent
- Job Matching Agent
- Customer Support Agent

---

# When to Use Multi-Agent Systems

Use multiple agents when:

- Tasks are large
- Multiple specializations are required
- Parallel processing is beneficial
- Complex coordination is needed

Examples:

- Research Platforms
- Business Intelligence Systems
- Enterprise Knowledge Systems
- Advanced Automation Platforms

---

# Mental Model

Think of:

```text
Single Agent
=
Generalist Employee
```

---

and

```text
Multi-Agent System
=
Specialized Team
```

Both can solve problems.

The difference is how the work is distributed.

---

# Evolution of AI Systems

```text
LLM
 ↓

AI Application
 ↓

RAG Application
 ↓

Single Agent
 ↓

Multi-Agent System
```

Each stage increases capability and complexity.

---

# Key Takeaways

- A Multi-Agent System consists of multiple agents working together.
- Agents can specialize in different responsibilities.
- Agents communicate through messages or shared memory.
- Multi-Agent Systems are useful for large and complex tasks.
- Single-agent systems are often sufficient for many real-world applications.
- Multi-Agent Systems increase flexibility but also increase complexity and cost.
- Most beginners should start with a single agent and multiple tools before building multi-agent architectures.
