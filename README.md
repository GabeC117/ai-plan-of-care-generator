# ai-plan-of-care-generator
Evaluates multiple prompt engineering strategies across LLM models for clinical Plan of Care generation, using an automated LLM auditor to compare constrained and unconstrained outputs across structured clinical criteria.


# AI-Assisted Plan of Care Generation & Clinical Audit System

## Overview
This project evaluates how different prompt engineering strategies perform across multiple large language models (GPT-4o and GPT-4o-mini) when generating therapy Plans of Care from clinical evaluation notes.
The system compares constrained and unconstrained prompting approaches and uses a secondary LLM auditor to score and analyze output quality in a high-risk healthcare documentation setting.

## Problem Context
Occupational and physical therapists often spend significant time converting evaluation notes into structured Plans of Care. This project explores whether large language models can assist in generating high-quality first drafts while maintaining safety through structured evaluation and auditing.

## Key Contribution
This project introduces a two-model pipeline:
1. A generation model creates a Plan of Care.
2. A second LLM acts as a clinical auditor that evaluates and compares outputs.
The auditor assigns structured scores and explanations, separating AI generation from evaluation similar to real-world AI validation workflows.

## System Workflow
Patient Evaluation Notes  
→ Prompt Strategy  
→ LLM Generation (GPT-4o / GPT-4o-mini)  
→ Clinical LLM Auditor  
→ Comparative Scores and Feedback

## Prompting Strategies Evaluated
- Baseline Prompt
- Poorly Structured Prompt
- Instructional Prompt
- Chain-of-Thought Prompting
- Constraint-Based Prompting
The project analyzes how reasoning structure and explicit clinical constraints influence documentation quality and safety.

## Automated Clinical Audit System
Generated Plans of Care are evaluated side-by-side using an LLM configured to act as a supervising occupational therapist.
Each output is scored across seven criteria:
1. Clarity & Formatting
2. Clinical Accuracy
3. Protocol Adherence
4. Goal Quality
5. Intervention Depth
6. Progression / Discharge Planning
7. Conciseness

Each category receives a score from 1–5 for a total score out of 35, along with qualitative feedback comparing both models.

## Key Findings
- Prompt structure significantly affects output quality.
- Larger models produced more consistent clinical reasoning.
- Constraint-based prompts improved safety adherence.
- Automated auditing enables scalable evaluation of high-risk AI outputs.

## Technologies Used
- Python
- OpenAI API
- Large Language Models (LLMs)
- Prompt Engineering
- AI Evaluation Pipelines

## Note
This project is a research prototype exploring AI-assisted clinical documentation workflows. Outputs require review by licensed healthcare professionals.

## Future Work
- Incorporating clinician feedback into the audit process
- Retrieval-Augmented Generation using clinical guidelines
- Expanding evaluation across additional models
- Exploring human-in-the-loop review workflows for safer deployment
