# Exercise 7 — Structured Outputs: JSON & Schema

## Objective

Ask an AI model to return football-player information in a defined JSON structure and check both syntax and requested fields.

## Scenario

The user supplies a football player's name. The model should return:
- Full player name.
- Current club.
- Nationality.
- All relevant playing positions.

The prompt required JSON output and instructed the model not to invent information; uncertain club information could be represented as `null`.

## JSON structure used

```json
{
  "player": "string",
  "club": "string or null",
  "nationality": "string or null",
  "positions": ["string"]
}
```

## Model tested

Grok.

## Test outputs

### Test 1 — Casemiro

```json
{
  "player": "Carlos Henrique Casimiro",
  "club": "Inter Miami",
  "nationality": "Brazil",
  "positions": ["Defensive Midfielder", "Centre-Back", "Central Midfielder"]
}
```

### Test 2 — Dani Carvajal

```json
{
  "player": "Daniel Carvajal Ramos",
  "club": "Getafe",
  "nationality": "Spain",
  "positions": ["Right-Back"]
}
```

### Test 3 — Rodri

```json
{
  "player": "Rodrigo Hernández Cascante",
  "club": "FC Barcelona",
  "nationality": "Spain",
  "positions": ["Defensive Midfielder", "Central Midfielder"]
}
```

### Test 4 — Sergio Ramos

```json
{
  "player": "Sergio Ramos García",
  "club": null,
  "nationality": "Spain",
  "positions": ["Centre-Back", "Right-Back"]
}
```

### Test 5 — Erling Haaland

```json
{
  "player": "Erling Braut Haaland",
  "club": "Manchester City",
  "nationality": "Norway",
  "positions": ["Centre-Forward", "Striker"]
}
```

## Haaland validation checks

The final Haaland output passed the five checks performed:

1. Player field present.
2. Club field present.
3. Nationality field present.
4. Positions field present.
5. JSON syntax valid.

Both “Centre-Forward” and “Striker” were accepted as relevant position labels in the exercise.

## Findings

- JSON provides a predictable structure for downstream use.
- A field can contain a string, `null`, or an array depending on the schema.
- Syntax validity and field presence are structural checks; they do not by themselves prove every fact is current or correct.
- The exercise tested multiple player names rather than only one example.

## Concepts demonstrated

- Structured outputs.
- JSON syntax.
- Schema and field expectations.
- Null handling.
- Structural validation.

## Conclusion

The five sample outputs were checked for the expected fields and JSON structure. The final Haaland example passed all five documented checks.
