# Tokenization in Large Language Models

## 1. What is Tokenization?

Tokenization is the process of converting raw text into smaller units called **tokens**, which can be processed by a machine learning model.

LLMs do not "see" words—they see token IDs.

---

## 2. Why Tokenization is Necessary

Neural networks cannot directly process text.

So we convert:

Text → Tokens → Token IDs → Embeddings → Model


---

## 3. What is a Token?

A token can be:

- A word
- A subword
- A character
- A punctuation symbol

Example:
"unbelievable" → ["un", "believ", "able"]


---

## 4. Tokenization is NOT Word Splitting

Unlike simple splitting by spaces:

"I love AI" → ["I", "love", "AI"]


Modern tokenizers split into subwords:

"unhappiness" → ["un", "happi", "ness"]


---

## 5. Token IDs

Each token is mapped to a numeric ID.

Example:
"hello" → 15496
"world" → 1917


These IDs are what the model actually processes.

---

## 6. Vocabulary (Vocab)

The tokenizer has a fixed vocabulary:

- Typically 30K → 200K tokens
- Each token has a unique ID

---

## 7. Why Subword Tokenization Exists

If we only used words:

Problems:
- Huge vocabulary
- Unknown words (OOV problem)

Subwords solve this by:
- Reusing common parts
- Handling unseen words

---

## 8. Unknown Words Problem (OOV)

Old NLP systems failed on unseen words.

Example:
"supercalifragilistic"


Modern tokenizers break it into known pieces.

---

## 9. Special Tokens

LLMs use special tokens for structure.

Examples:

- `<BOS>` → beginning of sequence
- `<EOS>` → end of sequence
- `<PAD>` → padding
- `<UNK>` → unknown token

---

## 10. Tokenization Pipeline


Raw Text
↓
Normalization
↓
Pre-tokenization
↓
Subword encoding
↓
Token IDs


---

## 11. Normalization Step

Before tokenization:

- Lowercasing (sometimes)
- Unicode normalization
- Removing inconsistencies

---

## 12. Tokenization Granularity

### Character-level:
- Very fine
- Long sequences

### Word-level:
- Simple
- Poor generalization

### Subword-level (BEST):
- Balanced
- Used in modern LLMs

---

## 13. Main Tokenization Algorithms

### 13.1 BPE (Byte Pair Encoding)

Most widely used method.

### Idea:
Merge frequent character pairs.

---

### Process:

1. Start with characters
2. Merge most frequent pairs
3. Repeat

---

### Example:
l o w
l o w e r
l o w e s t


Becomes:
"low", "er", "est"


---

### Why BPE works:
- Compresses frequent patterns
- Keeps rare words decomposed

---

## 14. WordPiece Tokenization

Used in models like BERT.

### Idea:
Maximize likelihood of training data.

Example:
"playing" → ["play", "##ing"]



---

## 15. Unigram Tokenization

Used in SentencePiece models.

### Idea:
Start with large vocab → remove least useful tokens.

---

## 16. SentencePiece

A tokenizer that:
- Treats text as raw input
- Does not require pre-splitting into words

Used in:
- T5
- LLaMA variants

---

## 17. Byte-Level Tokenization

Works at byte level instead of characters.

### Advantages:
- Handles any text
- No unknown tokens

Used in:
- GPT-style models

---

## 18. GPT Tokenizer (Conceptual)

GPT models typically use:

- Byte-level BPE
- Handles all Unicode text
- No OOV tokens

---

## 19. Tokenization Example (Full Pipeline)

Input: 
"Hello AI world!"


Steps:
1. Normalize text
2. Split into subwords
3. Map to IDs

Output:
[15496, 20185, 995]


---

## 20. Tokens vs Words (Critical Insight)

| Concept   | Words | Tokens |
|----------|------|--------|
| Granularity | coarse | fine |
| Flexibility | low | high |
| Vocabulary size | huge | controlled |

---

## 21. Why Tokenization Matters in LLMs

Tokenization affects:

- Cost (tokens = money)
- Context length
- Model performance
- Reasoning ability

---

## 22. Token Limits

Every model has max tokens:

Example:
- 4K
- 8K
- 32K
- 128K+

---

## 23. Token Explosion Problem

Some inputs expand unexpectedly:

Example:
- Spaces
- Code
- Emojis
- Non-English text

---

## 24. Multilingual Tokenization

Challenges:
- Different alphabets
- Different word structures

Solution:
- Subword + byte-level encoding

---

## 25. Code Tokenization

Code is often more token-heavy than natural language.

Example:
- symbols
- indentation
- punctuation

---

## 26. Emojis and Unicode

Modern tokenizers handle:

- Emojis 😀
- Special symbols
- Non-Latin scripts

---

## 27. Tokenization and Cost

LLM pricing depends on tokens:
cost ∝ input_tokens + output_tokens


---

## 28. Token Efficiency Tips

- Be concise
- Avoid repetition
- Reduce unnecessary context

---

## 29. Common Mistakes

- Assuming words = tokens
- Ignoring token limits
- Overloading prompts
- Not checking token cost

---

## 30. Mental Model

Think of tokenization as:

> “The translation layer between human language and machine-readable units.”

---

## 31. Summary

- LLMs operate on tokens, not words
- Tokenization is foundational
- Subword methods dominate modern systems
- Tokenization affects cost, performance, and behavior

---

## 32. Next Topics

- Inference optimization
- Prompt engineering patterns
- RAG systems
- Embeddings deep dive
- Agent systems

---

# End of Tokenization
