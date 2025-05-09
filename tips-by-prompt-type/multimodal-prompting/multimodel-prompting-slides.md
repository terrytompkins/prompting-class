---
marp: true
theme: default
paginate: true
size: 16:9
---

<!--
  Multimodal Prompting slide deck
  Convert with: marp multimodal-prompting.md -o multimodal-prompting.pdf
-->

# Multimodal Prompting  
## Mixing **text, images, and more** for richer AI results  

Class series • Prompt Engineering 104

---

## Why multimodal?

- Many business questions are *visual* (design review, diagram explanation, UI feedback).  
- Text‑only prompts miss context that a picture (or PDF, audio, etc.) conveys instantly.  
- Models now support **vision + text → text**, and **text → image generation**.  
- Unlocks new workflows: accessibility, marketing creatives, data‑viz explanations.

---

## What it is

> **Combining two or more input / output modalities in one task**  

| Direction | Examples |
|---|---|
| *Image → Text* | Describe, tag, extract data, critique design |
| *Text → Image* | Generate diagrams, mock‑ups, stock photos |
| *Image+Text → Text* | “Given this bar chart and caption, write the key insights.” |
| *Text → Image → Text loop* | Draft storyboard → generate frames → ask model to refine plot |

---

## Supported modalities (GPT‑4o class models)

- **Inputs**: Text, pasted image(s) or screenshot, PDF page, (beta: audio clip)  
- **Outputs**: Text; images via image‑gen or external tools (DALL·E 3, Stable Diffusion)  
- *Note*: Audio out is TTS–layer outside prompt scope.

---

## Basic prompt patterns

### A. Describe an image

```txt
<attach image>
You are a UX researcher.
Describe what you see: layout, color palette, and any usability issues.
Output as: 1) Plain description, 2) Issues (bullet list).
