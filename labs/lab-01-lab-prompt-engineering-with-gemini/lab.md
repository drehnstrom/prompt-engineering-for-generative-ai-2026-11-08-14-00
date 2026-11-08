# Prompt Engineering with Gemini

## Time Required

45 minutes

## Overview

In this lab, you will apply prompt engineering fundamentals using Gemini. You transition from loose, unstructured queries to highly structured prompts by incorporating roles, specific context, strict constraints, few-shot examples, and chain-of-thought reasoning.

### You learn how to:
- Compare baseline loose queries with structured role-based prompts.
- Apply formatting rules and length constraints to control output structure.
- Use few-shot prompting with examples to guide model classification tasks.
- Construct chain-of-thought reasoning prompts for complex problem-solving.

## Scenario

Your organization is adopting generative AI tools to assist with technical communication, architecture planning, and support triage. Team members often receive generic or inaccurate responses because they use vague, unstructured prompts. Your goal is to practice crafting precise, professional prompts that reliably yield production-ready results in Gemini.

## Lab Instructions

### Task 1: Compare baseline and structured role prompting

In this task, you test how assigning a specific persona and background context transforms a generic model response into a targeted business artifact.

1. Open your web browser and navigate to [Gemini](https://gemini.google.com).

2. Enter a loose baseline prompt asking the model to explain a technical concept:

```text
Explain cloud computing to a manager.
```

3. Review the output and note its tone, length, and level of detail.

4. Refine your prompt by adding a role, audience context, and specific constraints:

```text
Act as a principal cloud architect. Explain cloud computing to a non-technical Chief Financial Officer in two paragraphs, focusing on cost flexibility, scalability, and risk reduction. Avoid deep technical jargon like container orchestration or network virtualization.
```

5. Compare the structured output with your initial baseline query and observe how persona and context sharpen the response.

> [!NOTE]
> Notice how specifying the audience and persona instantly calibrates the vocabulary and perspective of the generated text.

### Task 2: Enforce constraints and output formatting

In this task, you add strict formatting and length limitations to control how Gemini structures its output data.

1. Create a prompt that requests a architectural comparison and mandates a specific tabular format:

```text
Compare public cloud, private cloud, and hybrid cloud architectures. 
Provide your response strictly as a markdown table with columns: Architecture, Key Advantage, Primary Risk, and Ideal Use Case. 
Limit each table cell to a maximum of 15 words.
```

2. Review the generated response to verify that it respects the markdown table structure and adheres to the cell length limits.

3. If the model included conversational intro or outro text, refine your prompt to include a negative constraint:

```text
Do not include any introductory or concluding conversational text. Output only the markdown table.
```

> [!IMPORTANT]
> Explicitly stating output formats such as markdown tables or JSON prevents the model from generating unwanted conversational filler.

### Task 3: Use few-shot prompting for classification

In this task, you provide input-output examples (few-shot prompting) to teach Gemini how to classify IT support requests consistently.

1. Construct a few-shot prompt that includes training examples before the target input:

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

2. Submit the prompt to Gemini and observe whether it correctly completes the pattern with `Application`.

3. Test your few-shot prompt with a new unclassified ticket of your own choosing.

> [!TIP]
> Providing 2 to 3 well-chosen examples establishes pattern rhythm and classification accuracy much faster than abstract rules alone.

### Task 4: Practice chain-of-thought reasoning

In this task, you prompt Gemini to reason step by step before generating a complex technical migration strategy.

1. Enter a complex problem prompt without reasoning instructions:

```text
Propose a strategy for migrating a live e-commerce platform database with 50,000 active users with zero downtime.
```

2. Review the output to see if the model rushed to conclusions without addressing intermediate risks.

3. Refine the prompt to enforce chain-of-thought reasoning:

```text
A development team is planning a zero-downtime database migration for a live e-commerce platform with 50,000 active users. 
Think step by step through potential risks, database schema compatibility challenges, and rollback procedures before proposing a 3-step migration strategy.
```

4. Compare the second output and examine how intermediate reasoning steps improve the quality and safety of the final proposal.

> [!WARNING]
> Forcing intermediate reasoning prevents the model from jumping straight to premature or flawed conclusions on complex tasks.

## Congratulations!

In this lab, you have:
- Compared baseline loose queries with structured role-based prompts.
- Applied formatting rules and length constraints to control output structure.
- Used few-shot prompting with examples to guide model classification tasks.
- Constructed chain-of-thought reasoning prompts for complex problem-solving.
