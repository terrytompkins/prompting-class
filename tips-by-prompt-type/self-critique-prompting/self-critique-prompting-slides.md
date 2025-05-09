---
marp: true
theme: default
paginate: true
size: 16:9
---

<!--
  Iterative / Self‑Critique Prompting slide deck
  Convert with: marp self‑critique-prompting.md -o self‑critique-prompting.pdf
-->

# Iterative Prompting  
## Let the model **critique & improve its own output**

Class series • Prompt Engineering 103

---

## Why it matters

- First draft ≠ best draft — LLMs usually “write and forget.”  
- **Self‑critique** turns the model into its own editor.  
- Reduces hallucinations & improves structure without extra plugins.  
- Works even when you *can’t* supply examples.

---

## What it is

> **Ask the model to 1) answer, 2) evaluate that answer, 3) revise**  
> (all inside one prompt or as a loop)

Iterations may be:  
1. **Answer**  
2. **Critique** (quality, correctness, style)  
3. **Improve** → repeat until criteria met or max rounds reached

---

## Basic one‑shot pattern

```txt
<Your initial task>

Step 1 — Draft the answer.  
Step 2 — Assess the draft for {accuracy, completeness, style}.  
Step 3 — Rewrite the answer, fixing issues found in Step 2.  
Return only the rewritten answer.
