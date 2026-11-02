# Exercise 6 — Prompt Refinement Loop

## Objective

Demonstrate iterative prompt refinement by generating outputs, evaluating them, identifying weaknesses, modifying the prompt and comparing later versions.

## Existing project reused

**Prompt Evolution Lab** — a practical experiment exploring how prompt specificity and context affect AI-generated football images.

The project was completed during the earlier IBM prompt-engineering learning track. It was reused here because it already demonstrates the core refinement cycle. A duplicate project was not created.

The complete original project files are included in this folder under `Prompt-Evolution-Lab/`, including the exact V1–V3 prompts, generated images, comparison notes and concepts-used notes.

## Workflow and versions

### V1 — Baseline

Exact prompt:

> Generate a football stadium image.

Purpose: establish a baseline using a broad, simple instruction.

Observed result:
- Wide-angle football stadium scene.
- Many stadium and crowd details.
- Overall appearance judged somewhat artificial.
- Scoreboard contained incorrect or unintended team text when inspected.

### V2 — Specific prompt

Exact prompt:

> Generate a football stadium with blueas the main theme colour. Show two teams playing a football match, viewed from the stands.

Purpose: add a dominant colour theme and specify two teams playing.

The spelling `blueas` is preserved because it appeared in the prompt used for the experiment.

User observations:
- Team logos/emblems were clearer than in V1.
- Blue-team jerseys were more clearly represented.
- The blue theme was more prominent.
- Scoreboard and team-related details made the match presentation more specific.
- Both V1 and V2 still looked artificial.

### V3 — Context-rich prompt

Exact prompt:

> Create a realistic football match scene during El Clásico at the Santiago Bernabéu Stadium, featuring FC Barcelona vs Real Madrid.
>
> Capture the electric, intense atmosphere of this historic rivalry. Since Real Madrid are playing at home, show the majority of the stadium filled with Real Madrid supporters wearing white, while a clearly defined away-fan section is occupied by Barcelona supporters wearing blue and garnet.
>
> Make the players' jerseys clearly distinguishable and recognisable: Real Madrid players wearing their traditional white kits, and Barcelona players wearing their traditional blue-and-garnet striped kits. Show both teams actively playing on the pitch.
>
> Use a wide-angle view from the stands, with the pitch, players, crowd, and both fan sections clearly visible. Emphasise the contrast between the two sets of supporters and the electric matchday atmosphere.

Purpose: add the match, venue, home/away supporter context, kit colours and atmosphere.

User-confirmed observations:
1. Strong rivalry atmosphere with distinct fan sections.
2. Home and away supporters clearly distinguishable.
3. White and blue-garnet kits distinguishable.
4. Stadium and match context clearly represented.
5. Somewhat realistic, with visible AI-like details.
6. Both teams and the pitch visible.

## Refinement-loop mapping

| Refinement-loop stage | Evidence in the project |
|---|---|
| Run | Generated V1, V2 and V3 images |
| Evaluate | Compared the generated images |
| Diagnose | Identified missing specificity, match context and visual details |
| Modify | Added progressively more specific instructions and context |
| Rerun | Generated later versions |
| Compare | Recorded differences and remaining limitations |

## Overall findings

- Moving from a generic prompt to a more specific prompt made the requested theme and match details more prominent.
- Adding match and venue context helped represent the intended El Clásico scene, including contrasting supporter sections and kits.
- AI-like details remained; greater prompt specificity did not fully resolve perceived realism.
- The wide-angle view showed the pitch and crowd, while individual players remained relatively small.
- Scoreboard text, scores and match times are generated image details, not verified real-world match information.

## Concepts demonstrated

- Zero-shot prompting: no example images were supplied as demonstrations.
- Clear instructions and specificity.
- Context.
- Iterative refinement.
- Output evaluation.
- Recording limitations and comparing versions.

## Important methodological note

The project progressively added multiple requirements between versions. It demonstrates an iterative refinement loop, but it does not isolate the effect of changing only one prompt variable at a time.

## Conclusion

Prompt Evolution Lab already provides practical evidence of the Prompt Refinement Loop. Reusing it avoided duplicating work and connected the earlier project to the advanced course concept.
