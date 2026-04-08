# AI-Assisted Plan of Care Generation & Clinical Audit System

## Overview

A research system that benchmarks prompt engineering strategies across LLMs for generating therapy Plans of Care from clinical evaluation notes. The core contribution is a two-model pipeline — a generation model paired with a secondary LLM auditor — that enables scalable, structured quality evaluation without human review at each step.

---

## Problem

Occupational and physical therapists spend significant time converting evaluation notes into structured Plans of Care. Poor documentation quality carries real clinical risk. This project explores whether LLMs can reliably generate high-quality first drafts across varying prompt structures, and whether a secondary model can serve as a scalable auditing layer in high-stakes healthcare documentation workflows.

---

## Product Design

### Two-Model Pipeline

```
Patient Evaluation Notes
        ↓
  Prompt Strategy
        ↓
  Generation Model (GPT-4o / GPT-4o-mini)
        ↓
  LLM Clinical Auditor
        ↓
  Structured Scores + Comparative Feedback
```

The auditor model is configured to act as a supervising occupational therapist, separating generation from evaluation — mirroring real-world AI validation practices.

---

## Prompt Strategies Evaluated

| Strategy | Description |
|---|---|
| Baseline | Minimal instruction prompt |
| Poorly Structured | Intentionally ambiguous, used as a quality floor |
| Instructional | Explicit step-by-step format guidance |
| Chain-of-Thought | Structured clinical reasoning before output |
| Constraint-Based | Hard safety and protocol constraints injected |

---

## Audit Criteria (Scored 1–5, Max 35)

1. Clarity & Formatting
2. Clinical Accuracy
3. Protocol Adherence
4. Goal Quality
5. Intervention Depth
6. Progression / Discharge Planning
7. Conciseness

Each Plan of Care is evaluated side-by-side with qualitative feedback comparing outputs across models and strategies.

---

## Key Findings

- Prompt structure is the strongest driver of output quality — more impactful than model size alone
- Constraint-based prompting produced the most consistent safety adherence across both models
- GPT-4o showed stronger clinical reasoning coherence; GPT-4o-mini degraded faster under loosely structured prompts
- Automated LLM auditing scales evaluation without requiring per-output clinician review

---

## Tech Stack

- Python
- OpenAI API (GPT-4o, GPT-4o-mini)
- Prompt engineering (5 strategies)
- LLM-as-evaluator pipeline

---

## Future Roadmap

- **RAG integration** — ground generation in clinical guidelines (e.g., AOTA practice frameworks)
- **Clinician-in-the-loop feedback** — capture licensed OT corrections to fine-tune audit scoring
- **Model expansion** — evaluate Claude, Gemini, and open-source clinical LLMs
- **Human-AI review workflows** — design handoff protocols for safer clinical deployment

---

> **Note:** This is a research prototype. All generated Plans of Care require review by a licensed healthcare professional before clinical use.
