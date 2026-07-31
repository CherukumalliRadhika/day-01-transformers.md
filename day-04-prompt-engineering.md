# Day 4: Prompt Engineering — Zero-Shot vs Few-Shot

## What I learned today
Prompt engineering is the practice of crafting inputs (prompts) to get the best 
possible output from a language model — without changing the model itself. 
Today I focused on two core prompting strategies: zero-shot and few-shot.

## Key Concepts

### 1. Zero-Shot Prompting
- You ask the model to perform a task **without giving any examples**.
- The model relies purely on its pre-trained knowledge to understand and complete the task.

**Example:**
Prompt: "Classify the sentiment of this review as Positive, Negative, or Neutral:
'The food was cold and the service was slow.'"

Output: Negative
- Works well for simple, common tasks the model has seen a lot during training.
- Can struggle with tasks that are ambiguous, niche, or require a specific output format.

### 2. Few-Shot Prompting
- You give the model **a few examples** of the task before asking it to perform 
  the same task on new input.
- This helps the model understand the exact pattern, format, or style you want.

**Example:**
Prompt:
Review: "Amazing food, quick service!" → Positive
Review: "Terrible experience, never going back." → Negative
Review: "It was okay, nothing special." → Neutral
Review: "The food was cold and the service was slow." →

Output: Negative
- Improves accuracy and consistency, especially for tasks with a specific format 
  or domain-specific language.
- Uses more tokens (cost/context), since examples are included every time.

### 3. Why wording changes output
- Small changes in phrasing, word order, or specificity can significantly affect the response.
- Example: "Summarize this in one sentence" vs "Give me a brief summary" can produce 
  different lengths and styles of output.
- Being explicit about format, tone, and constraints (length, style, structure) 
  generally produces more reliable results.

### 4. Other related techniques
- **One-shot prompting**: Just one example instead of several — a middle ground 
  between zero-shot and few-shot.
- **Chain-of-thought prompting**: Asking the model to "think step by step," which 
  improves performance on reasoning-heavy tasks.
- **Role prompting**: Assigning the model a persona (e.g., "You are an expert 
  data scientist...") to shape tone and depth of response.

## Why it matters
Prompt engineering is often the fastest, cheapest way to improve model output — 
no retraining or fine-tuning required. Understanding zero-shot vs few-shot helps 
decide when examples are worth the extra tokens versus relying on the model's 
built-in knowledge.

## Resources I used
- OpenAI Prompt Engineering Guide
- "Language Models are Few-Shot Learners" (GPT-3 paper, Brown et al., 2020)

## Tomorrow's plan
Explore fine-tuning vs RAG (Retrieval-Augmented Generation) — when to adapt a 
model's behavior versus feeding it external knowledge.
