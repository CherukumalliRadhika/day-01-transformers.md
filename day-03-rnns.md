# Day 3: RNNs — The Architecture Before Transformers

## What I learned today
Before Transformers took over, Recurrent Neural Networks (RNNs) were the go-to 
architecture for handling sequential data like text, speech, and time series.

## Key Concepts

### 1. What is an RNN?
A neural network designed to process sequences one element at a time, 
while maintaining a "memory" (hidden state) of what it has seen so far.

At each time step:
Example: Reading "The cat sat on the mat" — the RNN processes "The," updates its 
memory, then "cat" (now holding context of "The cat"), and so on, word by word.

### 2. Why RNNs were useful
- Could handle variable-length sequences (unlike basic feedforward networks).
- Captured some sense of order and context — useful for language and time-series tasks.

### 3. The big problems with RNNs

**Sequential processing = slow**
- Each step depends on the previous one, so RNNs can't be parallelized easily. 
  Training is slow, especially on long sequences.

**Vanishing/exploding gradients**
- On long sequences, gradients used to update weights can shrink to near-zero 
  or blow up, making it hard to learn long-range dependencies.
- Example: RNNs struggle to connect "it" back to a noun mentioned 20 words earlier.

**Short memory in practice**
- Despite having "memory," basic RNNs tend to forget information from many steps back.

### 4. Improvements over basic RNNs
- **LSTM (Long Short-Term Memory)** — adds gates (input, forget, output) to control 
  what information is kept or discarded, easing the vanishing gradient problem.
- **GRU (Gated Recurrent Unit)** — a simpler, faster version of LSTM with fewer 
  gates but similar performance.

### 5. Why Transformers replaced RNNs
- Transformers process the **entire sequence in parallel** using self-attention, 
  instead of step-by-step — much faster training.
- Self-attention connects any two tokens directly, regardless of distance, 
  handling long-range dependencies far better than RNNs.

## Why it matters
Understanding RNNs makes it clear *why* Transformers were such a breakthrough — 
they solved the two biggest RNN weaknesses (speed and long-range memory) in one shot.

## Resources I used
- Christopher Olah's "Understanding LSTM Networks" blog
- Andrej Karpathy's "The Unreasonable Effectiveness of RNNs"

## Tomorrow's plan
Explore prompt engineering — zero-shot vs few-shot prompting and how wording 
changes model output.
