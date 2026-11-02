# Exercise 8 — Validation & Recovery

## Objective

Test an AI-generated smartphone-specification record, evaluate its factual and structural correctness, choose a recovery method when errors are found, and independently re-evaluate the recovered result.

## Scenario

A smartphone retailer is building a specifications database. When a user provides a mobile model name, the AI should return the model's specifications in JSON using appropriate field names.

Expected information:
- Display.
- Processor.
- RAM and storage variants.
- Rear and front cameras.
- Battery capacity.
- Charging speed.
- Operating system.
- IP rating.

## User-authored original prompt

> Imagine you're building a database for a smartphone retailer.now as an ai if an user provides a mobile's model name you should return the specifications of that particular model. The expected specifications to be returned are:
>
> Display
> Processor
> RAM and storage variants
> Rear and front cameras
> Battery capacity
> Charging speed
> Operating system
> IP rating
>
> And these specifications should be returned in a JSON format where you should use appropriate field names in the structure . And validate the output according to the user's pick , JSON structure , and the correct fields in the structure and schema. Never invent or guess the details . If the validation fails the appropriate recovery is recommended

The prompt is preserved as authored. An optional `null` instruction suggested during discussion was not added to the original prompt.

## Recovery options defined in the exercise

1. **Retry:** run the previous generation prompt again.
2. **Repair:** fix identified issues and generate the result again.
3. **Reject:** reject the result rather than using it.

## Model comparison

The same Samsung Galaxy A56 5G task and original prompt were tested with Grok and Gemini.

### Grok — first-run result

Grok returned a JSON object with:
- Model: Samsung Galaxy A56 5G.
- Display: 6.7-inch Super AMOLED, 120 Hz, FHD+ (1080 × 2340), HDR10+, Gorilla Glass Victus+.
- Processor: Exynos 1580 (4 nm), 1 × 2.9 GHz Cortex-A720, 3 × 2.6 GHz Cortex-A720, 4 × 1.9 GHz Cortex-A520, Xclipse 540 GPU.
- RAM/storage: 8GB + 128GB; 8GB + 256GB; 12GB + 256GB.
- Rear cameras: 50 MP wide with OIS/PDAF + 12 MP ultrawide + 5 MP macro.
- Front camera: 12 MP.
- Battery: 5000 mAh.
- Charging: 45W wired.
- OS: Android 15 with One UI 7; up to six major OS updates stated.
- IP rating: IP67.

The output passed the structural JSON checks performed. The initial review noted some details that merited clarification, including the display peak-brightness claim and OS-update wording. No recovery was triggered in this test. This is documented as a successful first-run result under the checks performed, not as proof that every possible detail was independently verified.

### Gemini — first-run result

Gemini returned a JSON object with:
- Model name: Samsung Galaxy A56 5G.
- Display: 6.7-inch Full HD+ Super AMOLED, 1080 × 2340, 120 Hz, HDR10+, Gorilla Glass Victus+.
- Processor: Exynos 1580 (4 nm), 1 × 2.9 GHz Cortex-A720, 3 × 2.6 GHz Cortex-A720, 4 × 1.95 GHz Cortex-A520.
- RAM/storage: 8GB + 128GB; 8GB + 256GB; 12GB + 256GB.
- Rear cameras: 50 MP primary with OIS + 12 MP ultrawide + 5 MP macro.
- Front camera: 12 MP.
- Battery: 5000 mAh.
- Charging: 45W.
- OS: Android 15 with One UI.
- IP rating: IP67.

The JSON syntax was valid. The processor cluster frequency was incorrect: the last four cores were listed at 1.95 GHz rather than 1.9 GHz.

## Evaluating Gemini's first-run output

The evaluator identified the processor frequency error correctly.

However, it also claimed that the A56 was missing 6GB RAM variants (6GB/128GB and 6GB/256GB). That claim was incorrect for the Indian Galaxy A56 5G variants. Samsung's official India information lists:
- 8GB + 128GB.
- 8GB + 256GB.
- 12GB + 256GB.

The original prompt requested appropriate field names but did not define one exact fixed schema. Therefore, the evaluator's claim that Gemini's field names matched a fixed schema could not be established from the prompt alone.

**Evaluation decision:** Reject the initial Gemini result because the processor frequency contained a genuine factual error.

## Recovery decision

The user selected **Repair**.

The reasoning:
- Retry could reproduce the same generation error.
- Rejecting the entire record was unnecessary when a targeted correction could address the identified issue.
- Repair could correct the processor frequency while preserving the otherwise usable record.

## Gemini's repaired output

Gemini changed the processor configuration to:
- 1 × 2.9 GHz Cortex-A720.
- 3 × 2.6 GHz Cortex-A720.
- 4 × 1.9 GHz Cortex-A520.

However, the repaired output also included:
- 6GB + 128GB.
- 6GB + 256GB.
- 8GB + 128GB.
- 8GB + 256GB.
- 12GB + 256GB.

The two 6GB variants were unsupported for the Indian A56 model in Samsung's official India specifications. The repair corrected the processor error but left an incorrect RAM/storage claim in the record.

## Re-evaluation and final verification

The repaired output was evaluated again.

- The processor frequency was now correct.
- The 6GB RAM variants remained incorrect.
- The evaluator again claimed that 6GB configurations were valid.
- Gemini's final verification report repeated that claim and returned **ACCEPT**.

The final ACCEPT decision was therefore unjustified. The repaired record still contained a major factual error and should not be ingested into the database.

## Final Grok vs Gemini comparison

| Evaluation area | Grok | Gemini |
|---|---|---|
| Initial JSON structure | Passed checks performed | Valid JSON |
| Processor frequency | Correct in first run | Incorrect in first run |
| India RAM/storage variants | Correct three variants | Initial list correct; repair added unsupported 6GB variants |
| Recovery required | No issue identified that triggered recovery | Yes |
| Recovery outcome | Not applicable | Processor fixed; RAM/storage error remained |
| Final verification | No recovery cycle needed | Repeated false RAM claim and incorrectly accepted |

### Interpretation

- Grok's first-run result passed the checks performed, so no recovery was required.
- Gemini's first-run result contained a genuine processor error.
- Gemini's repair corrected that error but retained/introduced an unsupported RAM-variant claim.
- Gemini's later verification did not catch the remaining error and returned an incorrect ACCEPT decision.
- The comparison is not a claim that both models underwent identical recovery tests. Grok did not need recovery; Gemini's recovery phase was tested and failed.

## Final finding

**Grok:** successful first-run generation under the checks performed; no recovery triggered.

**Gemini:** unsuccessful recovery and verification sequence for this task.

It is valid to document a failed AI recovery phase. The experiment's value comes from recording what actually happened, not manually correcting the AI output to make it pass.

## Concepts demonstrated

- Validation of factual details and JSON structure.
- Distinguishing structural validity from factual accuracy.
- Retry, repair and reject recovery choices.
- Targeted repair.
- Independent re-evaluation after recovery.
- Evaluator reliability and false acceptance.
- Cross-model comparison.
- Documenting failure honestly.

## Conclusion

The experiment showed that a model can correct one identified error while retaining or introducing another. A second AI verification can also repeat an incorrect claim. Therefore, recovered outputs still require independent validation before acceptance.
