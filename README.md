# When Should Humans Take Over?

## Recent Errors and Authority under Imperfect Automation

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1mM6bZV-yfjKA-C0pycUg5f_y0gOGNzTO?usp=sharing)

This repository contains the research proposal, computational analysis, and supporting materials for my COMSCI/ECON 206 PS1 project.

The project studies whether recent automation error history changes human willingness to take control when the current economic state remains unchanged.

---

## Research Question

A human operator supervises an automated system and chooses between **Keep Auto** and **Take Over**.

The current state is described by:

- $p$ = automation reliability
- $L$ = loss if automation fails
- $C$ = cost of manual takeover

If automated control continues, its expected cost is

$$
EC_{\text{auto}}=(1-p)L
$$

The cost of manual takeover is

$$
EC_{\text{takeover}}=C
$$

Takeover is expected-cost optimal when

$$
C<(1-p)L
$$

The corresponding economic takeover boundary is

$$
p^*=1-\frac{C}{L}
$$

The behavioral question is whether recent error history changes human takeover decisions even when current $p$, $L$, and $C$ remain fixed.

---

## Repository Organization

The repository contains the PS1 paper source and a technical companion for the computational and interactive components.

```text
PS1_Lin/
├── companion/
│   ├── README.md
│   ├── requirements.txt
│   ├── notebooks/
│   │   └── takeover_boundary_analysis.ipynb
│   ├── outputs/
│   │   ├── economic_boundary.png
│   │   └── synthetic_takeover_boundaries.png
│   └── hf_space/
│       ├── README.md
│       └── index.html
└── README.md
```

The computational notebook, dependencies, actual outputs, Hugging Face source files, and reproduction instructions are documented in `companion/`.

---

## Computational Analysis

The notebook `companion/notebooks/takeover_boundary_analysis.ipynb` implements the computational part of the proposal.

It performs four main steps:

1. derives the expected-cost takeover boundary;
2. constructs matched Error and No Error scenarios;
3. generates synthetic choices for a computational check;
4. estimates and compares takeover boundaries across recent-history conditions.

For each history condition, the empirical takeover boundary is the reliability level at which the estimated probability of takeover equals 0.5.

The main computational quantity is

$$
\Delta p=\hat{p}_{E}-\hat{p}_{N}
$$

where:

- $\hat{p}_{E}$ is the estimated takeover boundary under Recent Error;
- $\hat{p}_{N}$ is the estimated takeover boundary under No Recent Error.

A positive $\Delta p$ means that the Error condition produces takeover at a higher stated automation reliability.

---

## Evidence Status

The notebook distinguishes three types of results.

### Derived economic result

The expected-cost boundary

$$
p^*=1-\frac{C}{L}
$$

is derived directly from the decision model.

### Actual computational outputs

The notebook produces actual computational outputs including:

- the economic takeover boundary;
- the matched scenario table;
- synthetic takeover probabilities and choices;
- estimated Error and No Error takeover boundaries;
- the estimated synthetic boundary shift;
- visualizations of the economic and synthetic takeover boundaries.

### Synthetic behavioral results

The behavioral choices in the notebook are synthetic.

They are generated from an assumed probability model only to verify that the computational procedure can recover a known boundary shift.

They do **not** establish how real human participants respond to recent automation errors.

A behavioral claim requires human choice data collected under the matched experimental design.

---

## Google Colab

The notebook can be run directly in Google Colab using the badge at the top of this README.

To reproduce the analysis:

1. Open `takeover_boundary_analysis.ipynb` in Google Colab.
2. Select **Runtime → Restart session and run all**.
3. Confirm that all cells execute without error.
4. Inspect the generated tables, boundary estimates, and figures.

The notebook uses the fixed random seed

```text
206
