# Large Language Models (LLMs) Basics

## 1. What is a Large Language Model?

A Large Language Model (LLM) is a deep learning model—typically based on the Transformer architecture—trained on massive amounts of text data to understand and generate human-like language.

---

## 2. Key Capabilities of LLMs

LLMs can:

- Generate text
- Answer questions
- Summarize documents
- Translate languages
- Write code
- Perform reasoning (limited but improving)

---

## 3. From NLP to LLMs

### Traditional NLP:
- Rule-based systems
- Feature engineering (TF-IDF, n-grams)
- Smaller models

### Modern NLP (LLMs):
- End-to-end learning
- Pretrained on large corpora
- Minimal task-specific tuning

---

## 4. Core Idea: Next Token Prediction

LLMs are trained to predict the next token given previous tokens.

Example:
Input: "The capital of France is"
Output: "Paris"


Mathematically:
P(w_t | w_1, w_2, ..., w_{t-1})


---

## 5. Tokens (Important!)

Text is broken into tokens before processing.

### Token types:
- Words
- Subwords
- Characters

Example:
"unbelievable" → ["un", "believ", "able"]


---

## 6. Transformer Architecture (High-Level)

LLMs are built on Transformers.

### Core components:
- Embedding layer
- Self-attention layers
- Feedforward layers
- Output projection

---

## 7. High-Level LLM Pipeline

Text → Tokenization → Embeddings → Transformer → Probabilities → Output Tokens


---

## 8. Embeddings

Tokens are converted into vectors.

### Why?
Neural networks operate on numbers, not text.

### Properties:
- Semantic similarity
- Dense representation

---

## 9. Self-Attention (Core Mechanism)

Allows model to weigh importance of each token relative to others.

### Example:
"The cat sat on the mat"


"sat" attends to:
- "cat" (subject)
- "mat" (context)

---

## 10. Attention Formula

Attention(Q, K, V) = softmax(QK^T / √d_k)V


---

## 11. Multi-Head Attention

Instead of one attention mechanism, multiple run in parallel.

### Benefits:
- Capture different relationships
- Improve representation power

---

## 12. Positional Encoding

Transformers have no inherent order awareness.

### Solution:
Add positional information to embeddings.

---

## 13. Pretraining

LLMs are trained on massive datasets:

- Books
- Websites
- Code
- Articles

### Objective:
Next-token prediction

---

## 14. Fine-Tuning

Adapt pretrained model to specific tasks.

### Examples:
- Chat models
- Domain-specific assistants

---

## 15. Instruction Tuning

Train model to follow instructions.

### Example:
"Summarize this text:"


---

## 16. RLHF (Reinforcement Learning from Human Feedback)

Improves alignment with human preferences.

### Steps:
1. Train base model
2. Collect human feedback
3. Train reward model
4. Optimize with RL

---

## 17. Inference (Generation Phase)

After training, model generates text token by token.

---

## 18. Decoding Strategies

### Greedy
- Always pick highest probability

### Sampling
- Random selection based on probability

### Top-k
- Choose from top k tokens

### Top-p (nucleus sampling)
- Choose from cumulative probability

---

## 19. Temperature

Controls randomness.

- Low → deterministic
- High → creative

---

## 20. Context Window

Maximum number of tokens model can process.

### Limitation:
- Long inputs may be truncated

---

## 21. Inside the Model: From Tokens to Output

### Step-by-step flow:

1. Tokens → converted to IDs
2. IDs → mapped to embeddings (vectors)
3. Embeddings → passed through Transformer layers
4. Final layer → produces logits
5. Logits → converted to probabilities (softmax)
6. Token selected → appended to sequence

---

## 22. Logits and Probabilities

### Logits:
Raw, unnormalized scores for each token.

### Softmax:

P(token_i) = e^{z_i} / Σ e^{z_j}


- Converts logits into probabilities
- Ensures values sum to 1

---

## 23. Hidden States

Each layer produces hidden representations.

### Think of them as:
- Intermediate "understanding" of the text
- Increasingly abstract representations

---

## 24. Depth vs Width

### Depth (layers):
- More reasoning steps
- More abstraction

### Width (hidden size):
- More capacity per layer

---

## 25. Scaling Laws

Empirical finding:

> Performance improves with:
- More data
- Bigger models
- More compute

### Approximate relationship:

Loss ∝ (Compute)^-α


---

## 26. Emergent Abilities

Capabilities that appear only at scale.

### Examples:
- Few-shot learning
- Chain-of-thought reasoning
- Code generation

---

## 27. Zero-shot, One-shot, Few-shot Learning

### Zero-shot:
No examples given

### One-shot:
One example

### Few-shot:
Multiple examples in prompt

---

## 28. In-Context Learning

Model learns patterns *within the prompt* without updating weights.

### Key insight:
Prompt acts as temporary training data

---

## 29. Hallucinations (Critical Concept)

LLMs can generate:
- Incorrect
- Fabricated
- Confidently wrong answers

### Why it happens:
- Trained to predict plausible text, not truth
- No grounding in real-time facts

---

### Types of Hallucinations:

1. Factual errors
2. Fabricated citations
3. Logical inconsistencies

---

### Mitigation Strategies:

- Retrieval-Augmented Generation (RAG)
- Better prompting
- Verification layers
- Fine-tuning

---

## 30. Determinism vs Stochasticity

LLM outputs are probabilistic.

### Deterministic:
- Temperature = 0
- Same input → same output

### Stochastic:
- Random sampling
- More creative outputs

---

## 31. Token Economics (VERY IMPORTANT)

### Costs depend on:
- Input tokens
- Output tokens

### Implications:
- Long prompts = expensive
- Inefficient prompts = wasteful

---

## 32. Latency Factors

- Model size
- Input length
- Output length
- Hardware

---

## 33. Throughput

Number of requests handled per second.

### Tradeoff:
- Larger models → slower throughput

---

## 34. Context Window Limitations

Problems:
- Truncation
- Lost information
- Attention dilution

---

### Solutions:
- Chunking
- Sliding window
- Retrieval (RAG)

---

## 35. Prompt Sensitivity

Small changes in prompt → large output differences.

### Example:
"Explain this simply"
vs
"Explain this technically"


---

## 36. Prompt Structure Matters

Better prompts include:
- Clear instructions
- Context
- Constraints
- Examples

---

## 37. System vs User Prompts

### System Prompt:
- Defines behavior
- High-level instructions

### User Prompt:
- Task-specific input

---

## 38. Open vs Closed Models

### Open Models:
- LLaMA
- Mistral
- Falcon

Pros:
- Customizable
- Self-hosted

Cons:
- Infra complexity

---

### Closed Models:
- API-based (e.g., OpenAI)

Pros:
- Easy to use
- High performance

Cons:
- Less control

---

## 39. Fine-Tuning vs Prompting

| Approach      | Pros                     | Cons                    |
|--------------|--------------------------|--------------------------|
| Prompting    | Fast, flexible           | Less control             |
| Fine-tuning  | More accurate            | Expensive, complex       |

---

## 40. Safety & Alignment

LLMs must be controlled to avoid:

- Harmful outputs
- Bias
- Misinformation

### Techniques:
- RLHF
- Content filtering
- Guardrails

---

## 41. LLM Architectures

### 41.1 Encoder-Only Models

Examples:
- BERT

### Characteristics:
- Bidirectional context
- Strong for understanding tasks

### Use Cases:
- Classification
- Named Entity Recognition
- Sentiment analysis

---

### 41.2 Decoder-Only Models (MOST IMPORTANT)

Examples:
- GPT-style models

### Characteristics:
- Autoregressive (left → right)
- Generate text token by token

### Use Cases:
- Chatbots
- Code generation
- Content creation

---

### 41.3 Encoder-Decoder Models

Examples:
- T5
- BART

### Characteristics:
- Encoder processes input
- Decoder generates output

### Use Cases:
- Translation
- Summarization

---

## 42. Chat Models vs Completion Models

### Completion Models:
- Input → continuation

Example:
"The future of AI is"


---

### Chat Models:
- Structured conversation

Format:
System: You are helpful
User: Question
Assistant: Answer


---

### Key Difference:
Chat models are optimized for dialogue and instruction-following.

---

## 43. Tool Usage (Function Calling)

LLMs can call external tools.

### Why?
LLMs alone cannot:
- Access real-time data
- Perform precise calculations
- Interact with APIs

---

### Example Tools:
- Search APIs
- Databases
- Calculators
- Code execution

---

### Flow:

1. User asks question
2. LLM decides to call tool
3. Tool returns data
4. LLM generates final answer

---

## 44. Retrieval-Augmented Generation (RAG)

Enhances LLMs with external knowledge.

---

### Pipeline:
Query → Embed → Retrieve → Inject Context → Generate


---

### Components:
- Embeddings
- Vector database
- Retriever
- LLM

---

### Benefits:
- Reduces hallucinations
- Uses up-to-date data
- Domain-specific knowledge

---

## 45. Memory in LLM Systems

### Types:

#### Short-Term Memory
- Current conversation
- Context window

#### Long-Term Memory
- Stored externally (DB, vector store)

---

### Implementation:
- Chat history
- Retrieval systems
- User profiles

---

## 46. Agents (High-Level Intro)

LLMs can act as agents that:

- Plan
- Use tools
- Take actions
- Iterate

---

### Agent Loop:
Think → Act → Observe → Repeat


---

## 47. Prompt Engineering (Preview)

Crafting inputs to control LLM behavior.

### Techniques:
- Role prompting
- Few-shot prompting
- Chain-of-thought

---

## 48. Chain-of-Thought (CoT)

Encourages reasoning.

### Example:
"Think step by step"


---

### Effect:
- Improves reasoning tasks
- More accurate outputs

---

## 49. System Design Patterns

### 49.1 Simple LLM App

User → Prompt → LLM → Output


---

### 49.2 LLM + RAG

User → Retriever → Context → LLM → Output


---

### 49.3 LLM + Tools

User → LLM → Tool → LLM → Output


---

### 49.4 Agent System

User → Agent → Tools + Memory → Output


---

## 50. Common Engineering Mistakes

### 50.1 Over-reliance on Prompting
- Sometimes you need RAG or fine-tuning

---

### 50.2 Ignoring Token Costs
- Leads to expensive systems

---

### 50.3 Poor Evaluation
- Hard to measure quality

---

### 50.4 No Guardrails
- Risky outputs

---

### 50.5 Bad Chunking in RAG
- Leads to irrelevant retrieval

---

## 51. Evaluation Challenges

LLMs are hard to evaluate because:

- Outputs are non-deterministic
- Multiple correct answers
- Quality is subjective

---

### Methods:
- Human evaluation
- LLM-as-a-judge
- Benchmarks

---

## 52. Latency vs Quality Tradeoff

| Factor        | Small Model | Large Model |
|--------------|------------|-------------|
| Speed        | Fast       | Slow        |
| Cost         | Low        | High        |
| Quality      | Lower      | Higher      |

---

## 53. Production Considerations

### Must handle:
- Rate limits
- Failures
- Retries
- Logging
- Monitoring

---

## 54. Guardrails

Control model outputs.

### Techniques:
- Prompt constraints
- Output validation
- Moderation APIs

---

## 55. Observability

Track:
- Inputs
- Outputs
- Errors
- Latency
- Token usage

---

## 56. Security Concerns

### Prompt Injection
- Malicious instructions inside input

### Data Leakage
- Sensitive info exposure

---

### Mitigation:
- Input sanitization
- Isolation
- Output filtering

---

## 57. LLM Application Stack

Typical stack:

- Frontend (UI)
- Backend (API)
- LLM API / model
- Vector DB (optional)
- Tools / integrations

---

## 58. Cheat Sheet Summary

- LLMs = next-token predictors
- Transformers power everything
- Prompting is powerful but limited
- RAG reduces hallucinations
- Tools extend capabilities
- Agents enable autonomy
- Token cost matters
- Evaluation is hard

---

## 59. Mental Model (IMPORTANT)

Think of an LLM as:

- A probability engine
- Trained on text
- Not a database
- Not always truthful
- Extremely powerful with the right system design

---

## 60. What to Learn Next

Continue with:

- Tokenization (deep dive)
- Inference optimization
- Prompt engineering
- RAG systems
- Agents
- LLM evaluation

---

# End of LLM Basics
