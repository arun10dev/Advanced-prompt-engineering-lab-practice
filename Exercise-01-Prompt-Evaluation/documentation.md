# Exercise 1 — Prompt Evaluation

## Objective

Compare two sentiment-classification prompts and observe how prompt wording affects the model's label and explanation.

## Scenario

A smartphone company wants an AI system to classify customer reviews. The review contains both positive and negative feedback.

## Prompts used

**Prompt A**

> Classify customer's review as positive or negative.

**Prompt B**

> Classify customer's review as positive or negative or neutral and give a valid reason for that.

## Test input

> The phone has an excellent display and performs smoothly, but the battery drains quickly and the camera quality is disappointing.

## Model tested

Gemini.

## Observed outputs

### Prompt A output

> This customer review is Mixed (leaning toward Negative due to the core performance compromises). While the customer highlights positive aspects—praising the excellent display and smooth performance—the review ultimately weighs heavily on critical pain points: the battery drains quickly and the camera quality is disappointing.

### Prompt B output

> Classification: Neutral (or Mixed). Reason: The review contains a balanced mix of positive and negative feedback of roughly equal weight. The customer praises the phone's display and performance, but equally criticizes its battery life and camera quality. Because the positive and conflicting negative elements offset each other without one side clearly dominating the overall sentiment, it cannot be classified as purely positive or negative.

## Evaluation and findings

- Prompt A did not constrain the output to the two requested labels; Gemini returned “Mixed”.
- Prompt B expanded the available labels to include Neutral and requested a reason.
- Prompt B gave more explanation, but Gemini still returned “Neutral (or Mixed)” rather than selecting exactly one label.
- The test demonstrates that adding a category and asking for a reason does not automatically enforce a single unambiguous classification.
- A useful next refinement would be to require exactly one label from the allowed set. This is a finding from the test, not a claim that a full evaluation set was completed in this exercise.

## Concepts demonstrated

- Clear instructions.
- Output constraints.
- Prompt specificity.
- Evaluating actual model output against the requested format.

## Conclusion

Prompt B produced a more detailed explanation, but neither prompt fully controlled the classification label. The key lesson is to make the allowed output choices and selection requirement explicit.
