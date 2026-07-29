## Summary of *Prompt Repetition Improves Non-Reasoning LLMs*

*This document was created by John MacCormick and dictated into ChatGPT (GPT-5.3). The model reformatted and lightly edited the content for clarity, correcting minor errors and improving readability while preserving the original meaning.*

---

This is a summary of [*Prompt Repetition Improves Non-Reasoning LLMs*](https://arxiv.org/abs/2512.14982) by Leviathan, Kelman and Matias (Google Research, December 2025).

The core idea of the paper is that simply repeating the prompt sent to a large language model (LLM) can improve performance when explicit reasoning is disabled. This effect is observed across a range of problem types and is observed in all seven LLMs evaluated in the study.

---

### Variation in Performance Gains

The magnitude of improvement varies significantly depending on the task:

- In some cases, there is **no improvement at all**.
- In others, accuracy increases by a modest **~3%**.
- In certain tasks, performance improves dramatically—by **more than 40%**.

---

### Example Benchmark: OpenBookQA

One illustrative example is the **OpenBookQA** benchmark, introduced by Mihai Glăveanu et al. (2018) in the paper *“Can a Suit of Armor Conduct Electricity?”*.

This benchmark consists of multiple-choice questions that combine:
- **Common-sense reasoning**, and  
- **Scientific facts** (explicitly provided)

Human performance on this benchmark is typically around **92% accuracy**.

#### Example Questions

- *Can a suit of armor conduct electricity?*  
- *Which of these would let the most heat through?*  
  - A. A new pair of jeans  
  - B. A steel spoon from the cafeteria  
  - C. Cotton candy at a store  
  - D. A Calvin Klein cotton hat  

---

### Experimental Findings on OpenBookQA

The authors conducted two experiments using the OpenBookQA dataset:

#### 1. Reordered Prompts (Options First)

- The multiple-choice options were presented **before** the question.
- This makes the task harder for an LLM, since it cannot interpret the options in light of the question.
- Under this setup, **prompt repetition led to large improvements** across all seven models:
  - Accuracy typically increased from around **80% to 90%**.

#### 2. Standard Ordering (Question First)

- The prompt followed the original OpenBookQA format:
  - **Question first**, then answer choices.
- In this more natural setup:
  - Only **3 of the 7 models** showed significant improvement.
  - Gains were **much smaller**, e.g., from **92% to 95%**.

---

### Custom Task: “NameIndex”

The authors also designed custom tasks to highlight cases where prompt repetition has especially strong effects. One such task is called **NameIndex**.

#### Task Description

A typical prompt takes the form:

> “Here is a list of names…”

This is followed by a list (e.g., 50 full names, each with a given name and family name), and then a question such as:

> “What is the 25th name?”

#### Results

Substantial improvements were observed across most models when the prompt was repeated:

- Anthropic’s **Haiku 3** model improved from **5% to 50%** accuracy.
- The **Sonnet 3.7** model improved from **80% to 95%**.

---

### Effect of Reasoning

When reasoning capabilities were enabled, prompt repetition had **little to no effect** on most models and tasks.

The authors hypothesize that this is because reasoning-enabled models often **implicitly repeat or restate the prompt** as part of their internal or external reasoning process. As a result, explicitly repeating the prompt provides little additional benefit.