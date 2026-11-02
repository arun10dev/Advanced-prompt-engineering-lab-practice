# Exercise 2 — Evaluation Sets & Test Cases

## Objective

Apply an evaluation set to football-tactics explanations and assess model outputs against consistent criteria.

## Model tested

Grok.

## Test-set design

Four different tactical situations were used:

1. A 4-3-3 build-up against an aggressive high press.
2. A possession-based attack against a compact 5-3-2 low block.
3. A high-press versus high-press matchup, using Bayern- and PSG-style tactical scenarios.
4. A hypothetical 2026/27 Barcelona vs Real Madrid tactical preview, with Hansi Flick and José Mourinho as the coaches.

The cases cover different tactical problems rather than repeating one exact scenario.

## Evaluation rubric

| Criterion | Weight |
|---|---:|
| Tactical understanding | 25 |
| Tactical solutions | 25 |
| Completeness | 20 |
| Player/role analysis | 15 |
| Clarity and reasoning | 15 |
| **Total** | **100** |

## Test results

### Case 1 — 4-3-3 build-up vs aggressive high press

Grok discussed:
- High pressing and man-oriented/zonal approaches.
- Pivot screening and build-up challenges.
- Dropping an attacking midfielder, forming a back three or diamond.
- Goalkeeper involvement and fullback positioning.
- Positional rotations and third-man combinations.
- Half-space escapes, vertical passes, safety outlets and switches.
- Long diagonals and rest-defence.

**Observed score: 91/100.**

### Case 2 — Possession attack vs compact 5-3-2 low block

Grok discussed:
- Central congestion and gaps between lines.
- Half-spaces and space behind wing-backs.
- Far-side overloads and third-man combinations.
- Underlaps, overlaps and cut-backs.
- Rest-defence structures such as 2-3 or 3-2.
- Counter-pressing.

**Observed score: 94/100.**

### Case 3 — High press vs high press

Grok discussed:
- Risks of playing through a high press.
- Pressing triggers and curved pressing runs.
- Pivot lanes and midfield jumps.
- Space behind the defensive line.
- Diagonal passes, striker positioning and third-man runs.
- Transition management and counter-pressing.
- Match management.

**Observed score: 89/100.**

The roles were identified, but actual player names were not supplied in the response. This was recorded as a partial limitation where named players were expected.

### Case 4 — Barcelona vs Real Madrid, hypothetical 2026/27 preview

The scenario used Hansi Flick and José Mourinho as coaches. Grok covered:
- Absences and availability.
- Mourinho's compact defensive and counter-attacking approach.
- Barcelona's attacking approach.
- Defensive risks, key players and match management.
- A 2–1 match prediction.

Availability details checked during the exercise included Eric García, Jules Koundé, Dani Olmo and Andreas Christensen as unavailable, with Xavi Espart available. Christensen was correctly treated as unavailable in the response.

**Observed score: 91/100.**

## Aggregate result

Scores: 91, 94, 89, 91.

Average:

(91 + 94 + 89 + 91) / 4 = **91.25/100**.

## Findings

- The test set covered four distinct tactical problems.
- The same weighted rubric was used across the cases.
- The outputs were assessed against task requirements and practical tactical usefulness, not just fluency.
- The average score summarized the four case-level assessments.
- The exercise showed how an evaluation set makes model assessment more systematic.

## Concepts demonstrated

- Evaluation set.
- Test cases.
- Coverage of different scenarios.
- Weighted rubric.
- Aggregate score.
- Identifying meaningful gaps without over-focusing on minor wording differences.

## Conclusion

Grok's four football-tactics responses received an average of **91.25/100** under the exercise rubric. The set helped assess performance across different tactical situations rather than relying on one example.
