# Lesson 01 – Uncertainty‑Indicator Prompting  
*Prompt Engineering Mini‑Series*

---

## 1. What & Why

**Definition –** Add explicit instructions that make the LLM qualify each of its statements with a confidence estimate (qualitative or quantitative) + optional justification.

| Why it matters | Notes |
|---|---|
| *Fight hallucinations* | Confidence flags draw attention to low‑certainty areas. |
| *Cross‑discipline value* | Research, legal, product, and support teams can judge when to verify. |
| *Grows AI literacy* | Highlights that LLMs produce probabilistic estimates, not facts. |

---

## 2. Confidence Scales

| Scale | Usage |
|---|---|
| **High / Medium / Low** | Easiest for non‑technical users. |
| **0–100 %** | Good when you need finer granularity or thresholds (e.g., *cite when < 80 %*). |

> **Suggested rubric**  
> *High* > 85 % · *Medium* 60‑85 % · *Low* < 60 %

---

## 3. Basic Prompt Pattern

```txt
<Your question or task>

Return a table:  
Claim | Confidence (H/M/L) | Reason (≤ 15 words).

Use the rubric: High > 85 %, Medium 60‑85 %, Low < 60 %.  
Cite a source whenever Confidence is Medium or Low.
```

---

## 4. Hands‑On Templates

### Template A – Research Brief with Confidence

```txt
You are an analyst preparing an internal briefing.
Topic: {{TOPIC}}
Scope: {{TIME_RANGE}} | Region: {{REGION}}

Provide 5 key findings in a table  
Finding | Confidence (H/M/L) | 1‑sentence reason (≤ 15 words).
```

### Template B – Decision Memo Risk Scan

```txt
Act as a risk‑management officer.
Decision: {{DECISION}}

List top 5 risks with  
Likelihood % | Impact (1‑5) | Mitigation (1 line).

Compute Residual‑risk = avg(Likelihood×Impact)  
State overall confidence (H/M/L).
```

### Template C – Creative Subject Lines + Originality Score

```txt
Write three email subject lines promoting {{PRODUCT}} to {{AUDIENCE}}.
After each, append “🤔 Originality confidence: X %”.
```

---

## 5. Quick Cheat‑Sheet

```
🧩 Uncertainty‑Indicator Prompting
Pattern → Task ➜ Claim + Confidence (+ Reason/Citation)

Pro Tips
• Ask for justification on Med/Low  
• Combine with Chain‑of‑Thought  
• Treat confidence as heuristic, not truth
```

---

## 6. Caveats & Best Practices

- Models can still over‑estimate themselves → validate critical info.  
- Confidence ≠ mathematical probability; treat as risk indicator.  
- Keep reasons short to avoid verbosity.

---

## 7. 60‑Minute Class Agenda

| Min | Activity |
|---|---|
| 0‑5 | Mini‑lecture |
| 5‑20 | Hands‑on A |
| 20‑35 | Hands‑on B |
| 35‑50 | Hands‑on C |
| 50‑55 | Q & A |
| 55‑60 | Wrap‑up & teaser |

---
