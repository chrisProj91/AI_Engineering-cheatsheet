# Prompt Engineering: Prompt Patterns

## 1. What is a Prompt Pattern?

A prompt pattern is a reusable structure for designing prompts that reliably produce high-quality outputs from LLMs.

Instead of guessing prompts, we use **structured templates**.

---

## 2. Why Prompt Patterns Matter

LLMs are:
- Probabilistic
- Sensitive to wording
- Highly context-dependent

Good prompts:
- Improve accuracy
- Reduce hallucinations
- Control output format
- Reduce token waste

---

## 3. Basic Instruction Pattern

### Structure:
Instruction + Context + Output format


### Example:
Summarize the following text in 3 bullet points:
[TEXT]


---

## 4. Role Prompting Pattern

Assign a role to the model.

### Structure:
You are a [ROLE]. Do [TASK].


### Example:
You are a senior software engineer. Explain this code clearly.


---

### Why it works:
- Activates domain-specific behavior
- Improves tone and depth

---

## 5. Few-Shot Prompting Pattern

Provide examples before the task.

### Structure:
Input → Output examples + new input


### Example:
Translate English to French:

English: Hello → French: Bonjour
English: Goodbye → French: Au revoir
English: Thank you → French:


---

### Why it works:
- Shows pattern explicitly
- Improves consistency

---

## 6. Zero-Shot Prompting

No examples provided.

### Example:
Classify this sentence as positive or negative:
"I love this product"


---

## 7. Chain-of-Thought (CoT) Pattern

Encourages step-by-step reasoning.

### Structure:
Think step by step before answering.


---

### Example:
A store sells 3 apples for $2. How much do 9 apples cost? Think step by step.


---

## 8. Structured Output Pattern

Force machine-readable output.

### Example:
Return the answer in JSON format:
{
"summary": "",
"keywords": []
}


---

## 9. Constraint Pattern

Add strict rules.

### Example:
Answer in exactly 3 bullet points. No more, no less.


---

## 10. Delimiter Pattern

Separate context clearly.

### Example:
Summarize the text between triple quotes:

"""
[TEXT]
"""


---

## 11. Step-by-Step Decomposition Pattern

Break complex tasks into steps.

### Example:
1. Identify key concepts
2. Explain each concept
3. Provide summary

4. ---

## 12. Self-Consistency Pattern

Generate multiple answers and select the most consistent.

### Idea:
- Run model multiple times
- Aggregate results

---

## 13. ReAct Pattern (Reason + Act)

Combines reasoning with tool usage.

### Structure:
Think → Act → Observe → Repeat


---

### Use case:
- Agents
- Tool-using LLMs
- Research systems

---

## 14. Plan-and-Solve Pattern

Force planning before execution.

### Example:
First, outline a plan. Then solve the problem.


---

## 15. Critique and Improve Pattern

Model evaluates its own output.

### Flow:

1. Generate answer
2. Critique it
3. Improve it

---

## 16. System Prompt Pattern

Defines global behavior.

### Example:
You are a helpful assistant that always responds concisely and accurately.


---

## 17. Multi-Turn Prompt Pattern

Use conversation history effectively.

### Key idea:
Each response depends on previous context.

---

## 18. Output Schema Pattern (Production Critical)

Used in APIs.

### Example:
Return valid JSON only:
{
"answer": string,
"confidence": number
}


---

## 19. Guardrail Pattern

Prevent unsafe or invalid outputs.

### Example:
If unsure, respond with "I don't know".


---

## 20. Context Injection Pattern (RAG-ready)

Insert external knowledge.

### Example:
Answer using ONLY the context below:
[CONTEXT]


---

## 21. Compression Pattern

Force concise outputs.

### Example:
Explain in under 50 words.


---

## 22. Expansion Pattern

Opposite of compression.

### Example:
Explain in detail with examples.


---

## 23. Comparative Pattern

Force comparison between concepts.

### Example:
Compare A vs B in terms of speed, cost, and scalability.


---

## 24. Evaluation Pattern

Ask model to judge outputs.

### Example:
Rate this answer from 1 to 10 and explain why.


---

## 25. Prompt Chaining Pattern

Break tasks into multiple prompts.

### Flow:
Prompt 1 → Extract info
Prompt 2 → Analyze
Prompt 3 → Final output


---

## 26. Production Best Practices

### DO:
- Be explicit
- Use structured formats
- Add constraints
- Test multiple prompts

---

### DON'T:
- Use vague instructions
- Overload context
- Assume model "understands intent"

---

## 27. Common Prompt Failures

- Ambiguity → wrong answers
- Missing constraints → messy outputs
- Over-long prompts → token waste
- No structure → inconsistent results

---

## 28. Mental Model of Prompting

Think of prompting as:

> "Programming an AI using natural language instead of code."

---

## 29. Summary

- Prompt patterns = reusable templates
- Structure improves reliability
- Constraints reduce hallucination
- RAG + prompts = powerful systems
- Good prompting = system design skill

---

## 30. Next Topics

- Prompt examples (real-world use cases)
- RAG systems
- LLM evaluation
- Agent architectures

---

# End of Prompt Patterns
