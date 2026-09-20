# PS1 Companion Materials

This directory contains the computational and interactive companion materials for:

**When Should Humans Stay in the Loop? Maintaining Human Capability under Automation Risk**

The current proposal is PS1 Version 2. Earlier Version 1 materials are retained to document the cumulative development of the project.

## Version 2 research question

Version 2 studies when manual control is worth an immediate performance cost because practice can preserve human capability for future periods in which automation becomes unavailable.

The computational benchmark treats human–automation allocation as a finite-horizon dynamic decision problem. Automation has a current performance advantage, but current allocation changes future human capability.

## Directory structure

### `hf_space_v2/`

Contains the Version 2 Hugging Face interactive game, **Stay in the Loop**.

The game implements a repeated human–automation allocation setting in which automation may become unavailable and human capability changes through practice or non-practice.

Live artifact:

https://huggingface.co/spaces/dku-comsci-econ206-2026/StayInTheLoop

### `notebooks/`

Contains the computational notebooks used for the PS1 analysis.

The Version 2 notebook implements:

- finite-horizon dynamic programming;
- recurring automation-unavailability risk;
- evolving human capability;
- state-dependent allocation decisions;
- a myopic baseline;
- low- and high-risk comparisons;
- capability-decay sensitivity analysis.

The main computational comparison uses per-period automation-unavailability probabilities of `q = 0.10` and `q = 0.30`.

Colab:

https://colab.research.google.com/drive/1pYMvzjzWt6SDJ0sRKy97mxhMXL35MklZ?usp=sharing

### `outputs/`

Contains selected outputs from the Version 2 computational benchmark, including the main voluntary-practice comparison and sensitivity analysis.

### `hf_space/`

Contains the earlier Version 1 interactive artifact. It is retained as part of the project's revision history.

### `src/` and `tests/`

Contain supporting code and tests retained from the companion repository structure.

## Model assumptions

The current Version 2 benchmark uses:

- horizon: `T = 12`;
- automation success probability: `p_A = 0.95`;
- initial human capability: `s_1 = 0.88`;
- failure loss: `L = 100`;
- capability decrease after automation use: `0.04`;
- capability increase after human control: `0.04`;
- capability bounds: `[0.56, 0.92]`;
- low automation-unavailability risk: `q = 0.10`;
- high automation-unavailability risk: `q = 0.30`.

These capability dynamics are synthetic modeling assumptions rather than empirical estimates.

## Computational interpretation

The dynamic-programming benchmark minimizes expected cumulative loss over possible future paths. Forced human-control rounds caused by automation unavailability are distinguished from voluntary manual-practice rounds.

The Hugging Face game represents one realized stochastic trajectory, whereas the notebook integrates over possible future paths. Realized game loss should therefore not be interpreted as policy quality.

## Reproducibility

To reproduce the Version 2 computational analysis:

1. Open `notebooks/ps1_v2_dynamic_allocation.ipynb`.
2. Install the dependencies listed in `requirements.txt`.
3. Restart the runtime.
4. Run all cells from beginning to end.
5. Compare the generated results with the files in `outputs/`.

The repository records the code and artifacts used for the submitted PS1 version.
