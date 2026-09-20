---
title: Stay in the Loop
colorFrom: blue
colorTo: green
sdk: static
pinned: false
---

# Stay in the Loop

A static educational game for the proposal **When Should Humans Stay in the Loop? Maintaining Human Capability under Automation Risk**.

## Research question

When should a person accept a short-run performance cost from manual practice in order to preserve human capability for future periods when automation may become unavailable?

## Game

You supervise an automated vehicle for **12 rounds**.

At the start of every round, automation is either:

- **Available**: choose **Use Automation** or **Practice Manual**.
- **Unavailable (Emergency)**: manual control is forced.

When automation is available:

- Automation succeeds with probability `p_A = 0.95`.
- Manual success depends on current human capability `s_t`.
- Choosing automation reduces next-round manual capability by `0.04`.
- Choosing manual control increases next-round capability by `0.04`.

Every operation has a realized outcome:

- Success: loss `0`
- Failure: loss `100`

The player therefore experiences actual stochastic losses during the game.

## Risk conditions

- **Low Risk:** `q = 0.10` probability that automation is unavailable in each round.
- **High Risk:** `q = 0.30` probability that automation is unavailable in each round.

Everything else is held fixed.

## Dynamic benchmark

The game also solves a finite-horizon dynamic program. The benchmark minimizes **expected cumulative loss**, accounting for:

1. current success probabilities,
2. the effect of today's allocation on future human capability, and
3. the probability that future rounds force manual control.

The benchmark is not shown during play. It is revealed on the results screen so the player's decisions are not directly guided by the optimal policy.

The results distinguish:

- **realized loss**, which depends on random outcomes, from
- **expected policy loss**, which evaluates the player's chosen voluntary actions under the model.

A player can therefore get lucky and have lower realized loss than the benchmark without having a better policy.

## Main comparison

The model tests the prediction:

`higher automation-unavailability risk -> greater value of preserved human capability -> more optimal manual practice`

Players are encouraged to replay under the other risk condition.

## Scope

Capability decay and recovery are synthetic assumptions for a classroom demonstration, not empirical estimates of real human skill. Game choices are not evidence of human behavior unless collected under an appropriate human-subject study design.

The Space is fully static and uses no backend, login, personal information, or external API.
