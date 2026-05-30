# 03 - Training and Weights

## What is Training?

Training is the process through which a model learns patterns from data.

The goal of training is to improve the model's ability to make predictions.

```text
Training Data
      ↓
Training Process
      ↓
Learned Model
```

After training, the model can generate predictions for new inputs.

---

## How Models Learn

Models learn through repeated practice.

Simplified process:

```text
Training Data
      ↓
Make Prediction
      ↓
Measure Error
      ↓
Adjust Weights
      ↓
Repeat
```

This process may happen millions or billions of times.

---

## Example of Learning

Training data:

```text
Dogs bark.
```

The model predicts:

```text
Dogs meow.
```

Wrong prediction.

The system detects the error and adjusts the model.

After many examples:

```text
Dogs bark.
```

becomes a much more likely prediction.

---

## Prediction Error

The model does not know whether it is correct until its prediction is compared against the expected answer.

Example:

Expected:

```text
bark
```

Predicted:

```text
meow
```

Result:

```text
Error Detected
```

The model then updates itself to reduce future errors.

---

## What are Weights?

Weights are learned numerical values inside a neural network.

They determine how strongly one pattern influences another pattern during prediction.

Simple definition:

> A weight represents the strength of a learned relationship.

---

## Understanding Weights

Think of weights as influence.

Example:

```text
Dog ----(strong influence)----> Bark

Dog ----(weak influence)----> Meow
```

The stronger the influence, the more likely a prediction becomes.

---

## Weights are NOT Facts

A common misconception is:

```text
Weight = Fact
```

Example:

```text
React is a library
```

is not stored in a single weight.

Instead:

```text
Millions of Weights
         ↓
Relationships
         ↓
Patterns
         ↓
Prediction
```

Knowledge emerges from many weights working together.

---

## How Weights Start

Before training:

```text
Weights = Random Numbers
```

Example:

```text
0.23
-0.91
1.52
0.07
```

At this stage the model has not learned anything useful.

---

## How Weights Change

Suppose the model repeatedly sees:

```text
Dogs bark.
Dogs bark.
Dogs bark.
```

During training:

```text
Dog → Bark
```

becomes stronger.

Incorrect relationships become weaker.

The model gradually improves through repeated adjustments.

---

## What Training Really Does

Training does not store facts like a database.

Instead:

```text
Training Data
      ↓
Find Patterns
      ↓
Adjust Weights
      ↓
Improve Predictions
```

The final model contains learned patterns rather than explicit records.

---

## Human Brain Analogy

Imagine learning something repeatedly.

Example:

```text
Dog → Bark
Dog → Bark
Dog → Bark
```

The association becomes stronger in your mind.

Similarly:

```text
Training Example
      ↓
Weight Adjustment
      ↓
Pattern Strengthens
```

Neural networks were inspired by the idea of interconnected neurons, although they are much simpler than the human brain.

---

## Patterns vs Facts

Traditional Database:

```json
{
  "React": "Library",
  "Node.js": "Runtime"
}
```

Stores explicit facts.

---

LLM:

```text
Patterns
      ↓
Relationships
      ↓
Predictions
```

Stores learned patterns through weights.

---

## Knowledge After Training

When training is finished:

```text
Training Data
      ↓
Learning
      ↓
Weights
      ↓
Model
```

The training data is not directly stored.

The learned patterns remain in the model's weights.

---

## Training Loop

The complete learning cycle:

```text
Training Data
      ↓
Prediction
      ↓
Error Detection
      ↓
Weight Adjustment
      ↓
Better Prediction
      ↓
Repeat
```

This loop is the foundation of modern machine learning.

---

## Key Takeaways

- Training is the process of learning patterns from data.
- Models improve by making predictions and correcting mistakes.
- Weights are learned numerical values inside the model.
- Weights represent the strength of learned relationships.
- Weights are not individual facts.
- Knowledge emerges from many weights working together.
- Training continuously adjusts weights to improve predictions.
- Modern AI models learn patterns rather than storing explicit records like databases.
