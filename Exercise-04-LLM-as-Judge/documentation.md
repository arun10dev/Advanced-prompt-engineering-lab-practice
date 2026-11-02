# Exercise 4 — LLM-as-Judge

## Objective

Use one language model to judge the outputs of two other model responses, then compare the judge's results with a human assessment.

## Scenario and source task

The exercise reused Exercise 2, Case 2: a possession-based attack against a compact 5-3-2 low block.

ChatGPT and Gemini responses to the same tactical task were compared. Grok acted as the LLM judge.

## Judge rubric

| Criterion | Weight |
|---|---:|
| Tactical understanding | 25 |
| Tactical solutions | 25 |
| Completeness | 20 |
| Tactical reasoning | 15 |
| Clarity | 15 |
| **Total** | **100** |

## LLM-as-Judge results

### Run 1

- ChatGPT: 95/100.
- Gemini: 88/100.

### Run 2 — response order reversed

- Gemini: 85/100.
- ChatGPT: 95/100.

The winning response remained the same after reversing the order. Gemini's score changed from 88 to 85, while ChatGPT's score remained 95.

These two runs did not show a winner reversal due to response order. They do not prove that the judge is free from position bias.

## Human evaluation

The user independently assessed the two responses using four equally weighted dimensions:

- Understanding.
- Tactical depth.
- Match-friendliness/practical usefulness.
- Completeness.

Human scores:
- Gemini: 83/100.
- ChatGPT: 96/100.

The user preferred ChatGPT because its response showed stronger structural understanding, connected tactical reasoning, practical match solutions, completeness, and graphic/visual representation. Visual representation was considered important for learning football tactics.

No significant factual errors were identified in either response during this comparison.

## Findings

- An LLM can be used as a judge with an explicit rubric.
- Reversing answer order is a useful basic check for position bias.
- The winner remained stable across the two judge runs.
- A stable winner does not establish that the judge is unbiased or fully reliable.
- Human evaluation provided an independent comparison point.
- Scores can vary even when the relative winner stays the same.

## Limitations

Only two judge runs were performed. This is not enough to establish general judge reliability or absence of bias. The human and AI rubrics were also not identical.

## Concepts demonstrated

- LLM-as-Judge.
- Weighted evaluation criteria.
- Position-bias check through order reversal.
- Human-versus-AI evaluation.
- Score variance and interpretation.

## Conclusion

Both the LLM judge and the user's human assessment selected ChatGPT's response as stronger for this task. The exercise demonstrated the value of a rubric and the need to validate an AI judge rather than treating its scores as ground truth.
