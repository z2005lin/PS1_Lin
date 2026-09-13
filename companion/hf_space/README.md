# Trust or Take Over?

This Hugging Face Space is an interactive decision game for a research proposal on human takeover under imperfect automation.

## Research question

When current automation reliability, failure loss, and takeover cost are fixed, does recent error history change a human operator's willingness to take control?

## Game idea

A human operator supervises an automated industrial vehicle. In each scenario, the player chooses one action:

- **Keep Auto** means the automated system continues operating.
- **Take Over** means the human operator intervenes manually.

Each scenario shows:

- automation reliability `p`
- failure loss `L`
- takeover cost `C`
- recent history, either **recent error** or **no recent error**

The economic benchmark compares expected automation cost with takeover cost:

```text
Expected automation cost = (1 - p) * L
Take over if C < (1 - p) * L
Keep auto if C > (1 - p) * L
```

The takeover boundary is:

```text
p* = 1 - C / L
```

The game uses matched scenario pairs. Within each pair, `p`, `L`, and `C` are identical. Only recent history changes. This makes it possible to observe whether recent error history changes the player's choice when the current economic state is unchanged.

## Outputs shown by the game

After all scenarios, the game reports:

- benchmark agreement rate
- takeover rate after recent error
- takeover rate after no recent error
- takeover difference between the two history conditions
- matched-pair switches
- choices near the economic takeover boundary

These outputs are educational and exploratory. They do not establish population-level human behavior.

## Files

- `index.html` contains the complete static game.
- No backend, database, API, or server runtime is used.

## How to run

Open the Hugging Face Space in a browser. The page runs as a static HTML file.

Local use is also possible by opening `index.html` directly in a browser.

## Responsible boundary

This game is a simplified research and teaching prototype. The scenarios are synthetic and do not represent real vehicle safety certification, real accident risk, or real operational advice. No personal information is collected.
