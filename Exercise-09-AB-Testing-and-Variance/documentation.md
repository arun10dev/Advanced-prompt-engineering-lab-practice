# Exercise 9 — A/B Testing & Variance

## Objective

Compare two prompt approaches and observe output differences across repeated runs using the same model.

## Scenario

A smartphone company wants a short, student-friendly product description for a fictional phone called NOVA X1.

## Supplied specifications

- Display: 6.7-inch AMOLED.
- Battery: 5000 mAh.
- Camera: 50 MP.
- Processor: Snapdragon 7 Gen series.

## Meta-prompts used

### Prompt A

> Generate a prompt for the description of a mobile phone called NOVA X1 and provide all the necessary details about the mobile like batter , model , display , processor , camera and others and this mobile is specifically launched for the students

### Prompt B

> Generate a detailed prompt for the description of a mobile phone called NOVA X1 and provide the details 1. Mobile brand 2.model 3.display 4.camera 5.processor 6. RAM 7. Storage 8. Clock speed 9. Charger capacity And the combined prompt do not exceed 100 lines and the prompt should feel more user friendly

## Generated prompt and output observations

### Prompt A output

Gemini generated a student-focused product-description prompt. It included:
- 6.5-inch FHD+ AMOLED display.
- Low Blue Light/DC Dimming.
- Octa-core processor.
- Up to 8GB dynamic RAM.
- 5000 mAh battery.
- 45W charging.
- 50 MP AI dual-camera.
- Front camera.
- 128GB/256GB storage and expandable storage claims.
- Study Mode and IP54.

Several details were not supplied in the original specification list and were generated as if they were product facts.

### Prompt B — Run 1

The generated description included:
- 6.5-inch OLED display.
- Octa-core processor.
- 2.8 GHz clock speed.
- 8GB RAM.
- 128GB storage.
- 48 MP camera.
- 65W charging.

Some supplied details were changed.

### Prompt B — Run 2

The generated description included:
- 6.6-inch FHD+ 120Hz Fluid AMOLED display.
- 3.0 GHz clock speed.
- 12GB RAM.
- 256GB storage.
- 64 MP camera.
- 80W charging.

The supplied 5000 mAh battery capacity was omitted.

## Findings

- The same Prompt B produced different specifications across two runs. This is observed run-to-run variance.
- Supplied specifications were changed, such as display size and camera resolution.
- Missing specifications were invented or presented without support.
- Run 2 omitted the supplied battery capacity.
- Polished marketing language did not guarantee factual accuracy.
- Variance and unsupported generation are related but different:
  - **Variance:** output changes between repeated runs.
  - **Unsupported generation:** output includes details not supported by the supplied information or reliable evidence.
- The results do not establish deliberate manipulation; the appropriate description is that the model altered, distorted or failed to preserve supplied facts.

## Suggested prompt constraints identified from the experiment

The findings suggest that a future prompt should:
- Use only supplied specifications.
- Preserve exact numbers, units and product names.
- Avoid guessing or inferring missing specifications.
- Mark unavailable details as “Not provided”.
- Check each generated claim against the supplied specification list.

These are lessons derived from the test, not a claim that the original prompts already contained these safeguards.

## Concepts demonstrated

- A/B prompt comparison.
- Repeated runs.
- Output variance.
- Factual consistency.
- Comparing prompt structure and output behavior.
- Distinguishing unsupported details from run-to-run variation.

## Conclusion

Prompt B's repeated runs produced different outputs, while both prompt approaches generated unsupported or altered specifications. The experiment showed why prompt comparison should evaluate factual preservation and consistency, not just presentation quality.
