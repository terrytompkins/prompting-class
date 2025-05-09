---
marp: true
theme: default
paginate: true
size: 16:9
---

<!--
  Uncertainty‑Indicator Prompting slide deck
  Convert with: marp uncertainty-prompting.md -o uncertainty-prompting.pdf
-->

# Uncertainty‑Indicator Prompting  
## Make the LLM tell you **how sure it is**

Class series • Prompt Engineering 102

---

## Why uncertainty matters

- Hallucinations = low‑probability guesses stated confidently  
- Regulatory, clinical, and financial decisions need **risk flags**  
- Knowing self‑estimated confidence helps you decide what to *double‑check*

---

## What it is

> **Ask the model to rate its own certainty**  
> &nbsp;  
> - Qualitative: **High / Medium / Low**  
> - Quantitative: **0 – 100 %**  
> - Optional: one‑sentence justification or citation when confidence ≤ Medium  

---

## Basic prompt pattern

```txt
<Your question or task>

Return a table with columns  
Claim | Confidence (H/M/L) | Reason (≤ 15 words).

Confidence rubric  
  • High = > 85 % likely correct  
  • Medium = 60‑85 %  
  • Low = < 60 %

Cite a source whenever Confidence is Medium or Low.
