# Lesson 02 – Iterative Prompting & Self‑Critique  
*Prompt Engineering Mini‑Series*

---

## 1. What & Why

**Definition –** A prompt pattern that makes the LLM  
1) draft an answer, 2) critique that draft, 3) revise it—optionally repeating.

| Benefit | Detail |
|---|---|
| Quality boost | Model becomes its own editor—catches style issues, gaps, errors. |
| Rapid iteration | No extra tools; embed the loop in one prompt. |
| Versatile | Works for copy, code, plans, even creative writing. |

---

## 2. Basic One‑Shot Loop

```txt
<Your task>

Step 1 — Draft the answer.  
Step 2 — Critique the draft for {accuracy, completeness, style}.  
Step 3 — Rewrite the answer, resolving issues from Step 2.  
Return only the rewritten answer.
```

For deeper polishing: repeat Steps 2‑3 up to 3 times or until *all* scores ≥ 8/10.

---

## 3. Hands‑On Templates

### Template A – Prompt‑Improvement Loop

```txt
Task: {{YOUR_TASK}}

-- Round 1 --
1️⃣ Draft answer.

-- Round 2 --
2️⃣ Score draft on Clarity, Depth, Brevity (1‑10 each).  
3️⃣ Rewrite any section scoring < 8.

-- Round 3 (optional) --
Repeat until every score ≥ 8 or 3 rounds total.
```

### Template B – Self‑QA Code Generator

```txt
You are Senior Python Dev.
Goal: {{FUNCTION_SPEC}}.

Pass 1 – Write function + docstring + tests.  
Pass 2 – Review code: bugs, edge cases, PEP‑8.  
Pass 3 – Output improved code only.
```

### Template C – Idea‑Rank‑Refine Brainstorm

```txt
Topic: {{TOPIC}}

Stage 1 – Generate 5 ideas.  
Stage 2 – Rate Novelty & Feasibility (1‑5).  
Stage 3 – Expand the top idea into a 150‑word concept note.
```

---

## 4. Cheat‑Sheet

```
🌀 Iterative / Self‑Critique Prompting
Cycle → Answer ➜ Critique ➜ Improve (≤ 3×)

Critique dimensions
• Accuracy • Completeness • Style • Compliance

Tips
• Use emojis (1️⃣ 2️⃣ 3️⃣) to separate steps  
• Cap rounds to save tokens  
• Provide an explicit scoring rubric
```

---

## 5. Caveats

- Extra tokens = extra cost & latency.  
- Model may “agree with itself”; ensure critique prompts encourage fault‑finding.  
- Monitor drift: too many rounds can over‑simplify or over‑complicate.

---

## 6. 60‑Minute Class Agenda

| Min | Activity |
|---|---|
| 0‑5 | Mini‑lecture |
| 5‑20 | Hands‑on A |
| 20‑35 | Hands‑on B |
| 35‑50 | Hands‑on C |
| 50‑55 | Q & A |
| 55‑60 | Wrap‑up & teaser |

---
