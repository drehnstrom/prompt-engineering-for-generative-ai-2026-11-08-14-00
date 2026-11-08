# Solution: Prompt Engineering with Gemini - Prompt Log

## Task 1: Baseline vs Structured Prompting

### Loose Baseline Prompt
```text
Explain cloud computing to a manager.
```
*Observation*: The response was overly verbose, used generic textbook definitions, and lacked specific business context or actionable executive takeaways.

### Structured Prompt
```text
Act as a principal cloud architect. Explain cloud computing to a non-technical Chief Financial Officer in two paragraphs, focusing on cost flexibility, scalability, and risk reduction. Avoid deep technical jargon like container orchestration or network virtualization.
```
*Observation*: The response immediately adopted an executive tone, focused on financial and operational benefits, avoided jargon, and adhered strictly to the two-paragraph constraint.

---

## Task 2: Constraints and Formatting

### Prompt with Formatting and Length Constraints
```text
Compare public cloud, private cloud, and hybrid cloud architectures. 
Provide your response strictly as a markdown table with columns: Architecture, Key Advantage, Primary Risk, and Ideal Use Case. 
Limit each table cell to a maximum of 15 words.
```
*Observation*: The output successfully rendered as a clean markdown table, organized the comparison clearly, and kept cell descriptions concise.

---

## Task 3: Few-Shot Prompting

### Few-Shot Classification Prompt
```text
Classify incoming IT support tickets into one of three categories: Security, Infrastructure, or Application.

Example 1:
Input: "User reports password expired and MFA token is locked out."
Category: Security

Example 2:
Input: "Production database CPU utilization is at 98%."
Category: Infrastructure

Input: "The checkout button returns a 500 error when clicked."
Category:
```
*Observation*: The model successfully completed the pattern and returned `Category: Application` without adding unnecessary conversational filler.

---

## Task 4: Chain-of-Thought Reasoning

### Chain-of-Thought Prompt
```text
A development team is planning a zero-downtime database migration for a live e-commerce platform with 50,000 active users. 
Think step by step through the potential risks, database schema compatibility challenges, and rollback procedures before proposing a 3-step migration strategy.
```
*Observation*: The model detailed intermediate reasoning regarding read-write locks and backward compatibility before presenting a structured, logical 3-step mitigation plan.
