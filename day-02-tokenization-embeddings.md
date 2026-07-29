# Day 2: Tokenization & Embeddings

## What I learned today
Before a Transformer can process text, it needs to convert words into numbers. 
This happens in two steps: **tokenization** and **embedding**.

## Key Concepts

### 1. Tokenization
- Splitting raw text into smaller units called "tokens."
- Tokens can be whole words, subwords, or even characters, depending on the method.
- Example: "unbelievable" might be split into ["un", "believ", "able"] using subword tokenization.

**Common tokenization methods:**
- **Word-level**: Each word is a token (simple but huge vocabulary, struggles with rare words).
- **Character-level**: Each character is a token (small vocabulary, but loses word meaning easily).
- **Subword-level (BPE, WordPiece)**: Splits rare words into meaningful chunks, balances vocabulary size and meaning. This is what GPT, BERT, and most modern models use.

### 2. Why subword tokenization wins
- Handles unseen/rare words gracefully (e.g., "unhappiness" → "un" + "happi" + "ness").
- Keeps vocabulary size manageable (tens of thousands of tokens instead of millions of unique words).
- Reduces the "out-of-vocabulary" problem common in older NLP systems.

### 3. Embeddings
- Once text is tokenized, each token is converted into a vector of numbers (an embedding).
- These vectors capture semantic meaning — words with similar meaning end up with similar vectors.
- Example: The vectors for "king" and "queen" are closer to each other than "king" and "banana."

### 4. Why embeddings matter
- Neural networks can't work with raw text — they need numerical input.
- Good embeddings let the model understand relationships like:
  `king - man + woman ≈ queen`
- Embeddings are learned during training, so they improve as the model sees more data.

## Why it matters
Tokenization and embeddings are the entry point of every AI language model. 
If tokenization is inefficient, the model wastes capacity on splitting words awkwardly. 
If embeddings are poor, the model struggles to understand meaning and context.

## Resources I used
- Hugging Face NLP Course (Tokenizers chapter)
- "Word2Vec" and "GloVe" papers for embedding fundamentals

## Tomorrow's plan
Explore prompt engineering — zero-shot vs few-shot prompting and how wording changes model output.
