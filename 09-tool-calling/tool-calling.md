# 09 - Tool Calling

## Introduction

LLMs are excellent at understanding language, reasoning, and generating text.

However, they cannot directly perform actions in the real world.

Examples:

- Send emails
- Search live job listings
- Query databases
- Generate PDF files
- Access external APIs

Tool Calling solves this problem.

---

## What is Tool Calling?

Tool Calling is the mechanism that allows an LLM to request the use of external tools to perform actions.

Simple idea:

```text
LLM
 ↓
Choose Tool
 ↓
Tool Executes
 ↓
Result
 ↓
LLM
 ↓
Response
```

---

## Why Tool Calling Exists

LLMs can:

- Think
- Analyze
- Reason
- Plan

LLMs cannot:

- Send emails
- Search live data
- Execute backend functions
- Create files
- Access external systems directly

Without Tool Calling:

```text
User
 ↓
LLM
 ↓
Text Response
```

With Tool Calling:

```text
User
 ↓
LLM
 ↓
Tool
 ↓
Result
 ↓
LLM
 ↓
Final Response
```

This allows AI systems to perform actions instead of only generating text.

---

## What is a Tool?

A tool is a capability that performs a specific action.

Examples:

```javascript
searchJobs(skill);

sendEmail(to, subject, body);

generatePDF(content);

queryDatabase(query);
```

A tool does not think.

A tool does not reason.

A tool only performs its assigned task.

---

## LLM vs Tool

### LLM

Responsible for:

- Understanding requests
- Reasoning
- Planning
- Choosing tools
- Interpreting results

---

### Tool

Responsible for:

- Performing actions
- Returning results

---

Simple comparison:

| LLM           | Tool            |
| ------------- | --------------- |
| Thinks        | Executes        |
| Plans         | Performs Action |
| Chooses Tools | Returns Results |
| Reasons       | Does Not Reason |

---

## Function Calling

Tool Calling is often implemented using Function Calling.

The backend exposes functions:

```javascript
searchJobs(skill);

generatePDF(content);

sendEmail(to, subject, body);
```

The LLM is informed that these functions exist.

---

## Example

User:

```text
Find React jobs.
```

The LLM determines:

```text
Need job search capability.
```

Instead of answering immediately, it requests:

```json
{
  "tool": "searchJobs",
  "arguments": {
    "skill": "React"
  }
}
```

This is called a function call request.

---

## Important Understanding

The LLM does not execute code.

The LLM only requests:

```text
Use this tool
with these arguments
```

The backend executes the actual function.

---

## Tool Calling Flow

### Step 1

User submits a request.

```text
Find React jobs.
```

---

### Step 2

LLM analyzes the request.

```text
Need searchJobs()
```

---

### Step 3

LLM generates a function call request.

```json
{
  "tool": "searchJobs",
  "arguments": {
    "skill": "React"
  }
}
```

---

### Step 4

Backend executes the function.

```javascript
searchJobs("React");
```

---

### Step 5

Tool returns results.

Example:

```json
[
  {
    "title": "React Developer"
  },
  {
    "title": "Frontend Engineer"
  }
]
```

---

### Step 6

Results are sent back to the LLM.

---

### Step 7

LLM generates a user-friendly response.

```text
I found the following React jobs...
```

---

## Complete Architecture

```text
User
 ↓

LLM
 ↓

Function Call Request
 ↓

Backend
 ↓

Tool
 ↓

Tool Result
 ↓

LLM
 ↓

Final Response
```

---

## Why Two LLM Interactions Often Happen

Most tool-calling systems involve two LLM interactions.

### First LLM Call

Determine:

```text
Which tool should be used?
```

---

### Tool Execution

Execute the selected tool.

---

### Second LLM Call

Determine:

```text
How should the result be explained?
```

---

Example:

```text
User
 ↓

LLM
 ↓

Tool
 ↓

LLM
 ↓

Answer
```

---

## Common Tool Types

### Search Tools

Purpose:

```text
Retrieve live information
```

Examples:

- Job Search
- Web Search
- News Search

---

### Database Tools

Purpose:

```text
Retrieve stored data
```

Examples:

- User Information
- Customer Records
- Product Data

---

### Communication Tools

Purpose:

```text
Send information
```

Examples:

- Email
- SMS
- Notifications

---

### File Tools

Purpose:

```text
Create or process files
```

Examples:

- PDF Generation
- CSV Export
- File Uploads

---

### API Tools

Purpose:

```text
Interact with external systems
```

Examples:

- Weather APIs
- Payment APIs
- Calendar APIs

---

## Real Example: Resume Agent

Available Tools:

```text
readResume()

searchJobs()

generatePDF()
```

User Request:

```text
Create a tailored resume for React jobs.
```

Possible Tool Calls:

```text
readResume()
 ↓

searchJobs()
 ↓

generatePDF()
```

The LLM decides which tools are required and in what order.

---

## Important Mental Model

Think of:

```text
LLM = Brain
```

and

```text
Tools = Hands
```

The brain decides.

The hands perform actions.

---

## Tool Calling vs Agent

Tool Calling:

```text
Choose Tool
 ↓
Execute Tool
```

One decision.

---

Agent:

```text
Goal
 ↓
Reason
 ↓
Choose Tool
 ↓
Observe Result
 ↓
Choose Next Tool
 ↓
Goal Achieved
```

Multiple decisions.

---

## Key Takeaways

- Tool Calling allows LLMs to interact with external systems.
- Tools perform actions; LLMs make decisions.
- Function Calling is a common implementation of Tool Calling.
- The LLM never executes code directly.
- The backend executes the requested functions.
- Tool results are returned to the LLM for interpretation.
- Tool Calling enables AI systems to move beyond text generation.
- Tool Calling is a foundational capability of modern AI agents.
