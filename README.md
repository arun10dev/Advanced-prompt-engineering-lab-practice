# Advanced Prompt Engineering — Practical Exercises

## Overview

This repository documents nine practical exercises based on the course **Advanced Prompt Engineering: Evaluation, Meta-Prompting & Structured Outputs**.

The exercises apply prompt-engineering concepts through realistic tasks and observed model outputs. The practical work used free versions of Grok and Gemini where applicable. The goal was to test prompts, evaluate actual responses, record limitations, and distinguish successful outputs from failed attempts.

## Exercise tracker

| Exercise | Topic | Status |
|---|---|---|
| 1 | Prompt Evaluation | Completed |
| 2 | Evaluation Sets & Test Cases | Completed |
| 3 | Rubrics & Metrics | Completed |
| 4 | LLM-as-Judge | Completed |
| 5 | Meta-Prompting | Completed |
| 6 | Prompt Refinement Loop | Completed |
| 7 | Structured Outputs — JSON & Schema | Completed |
| 8 | Validation & Recovery | Completed |
| 9 | A/B Testing & Variance | Completed |
| 10 | Cost, Latency & Quality Trade-offs | Removed — not applicable to the available testing conditions |

**Final scope:** 9 retained exercises, all completed.

Exercise 10 was removed rather than marked complete. The practical setup used free versions of Grok and Gemini, so direct monetary cost was zero for both. A meaningful comparison of free-tier quotas would have required a time-consuming usage-limit experiment. The user chose not to force an artificial comparison.

## Repository structure

- `Exercise-01-Prompt-Evaluation/` — sentiment classification prompt comparison.
- `Exercise-02-Evaluation-Sets/` — four football-tactics test cases and weighted evaluation.
- `Exercise-03-Rubrics-and-Metrics/` — six-criterion smartphone review rubric.
- `Exercise-04-LLM-as-Judge/` — cross-model judging and order-reversal check.
- `Exercise-05-Meta-Prompting/` — generating a beginner football-learning prompt.
- `Exercise-06-Prompt-Refinement-Loop/` — documentation of the existing Prompt Evolution Lab project.
- `Exercise-07-Structured-Outputs/` — football-player information in JSON.
- `Exercise-08-Validation-and-Recovery/` — Samsung Galaxy A56 5G validation and Grok/Gemini comparison.
- `Exercise-09-AB-Testing-and-Variance/` — smartphone product-description prompt comparison.

## Important documentation principles

1. Exact prompts and observed outputs are preserved where available.
2. Results are described as observed in the experiment, not generalized to every model or every run.
3. A valid JSON structure does not guarantee factual accuracy.
4. An AI evaluator can itself make factual mistakes and must be independently checked.
5. Failed model behavior is a valid experimental finding; outputs are not manually corrected just to make an experiment look successful.
6. The Exercise 6 project is reused as evidence of iterative refinement. No duplicate project was created.
7. Exercise 10 is explicitly removed from the practical scope, not counted as completed.

## Completion summary

**9/9 retained practical exercises completed.**
