# When Should Humans Take Over?

## Recent Errors and Authority under Imperfect Automation

This repository contains the computational materials for the COMSCI/ECON 206 PS1 research proposal.

The project studies whether recent automation error history changes human willingness to take control when the current economic state remains unchanged.

## Research Question

The economic benchmark asks when human takeover is expected-cost optimal.

Let:

- `p` denote current automation reliability
- `L` denote the loss if automation fails
- `C` denote the cost of manual takeover

The expected cost of continued automation is

\[
(1-p)L
\]

while the cost of takeover is

\[
C.
\]

The expected-cost takeover boundary is

\[
p^* = 1 - \frac{C}{L}.
\]

The behavioral question asks whether recent error history shifts human takeover away from this economic boundary when current `p`, `L`, and `C` remain fixed.

## Computational Analysis

The notebook `takeover_boundary_analysis.ipynb` implements four steps:

1. derives the expected-cost takeover boundary;
2. constructs matched Error and No Error scenarios;
3. generates synthetic choices for a computational check;
4. estimates and compares takeover boundaries across recent-history conditions.

The main computational quantity is

\[
\Delta p
=
\hat p_E - \hat p_N,
\]

where:

- \(\hat p_E\) is the estimated takeover boundary after recent error history;
- \(\hat p_N\) is the estimated boundary under no recent error.

A positive value indicates that the synthetic Error condition produces takeover at higher stated automation reliability.

## Important Evidence Limitation

The behavioral choices used in the computational demonstration are synthetic.

They are generated from an assumed probability model in order to verify that the analysis pipeline can recover a known boundary shift.

The synthetic results do **not** establish how real human participants respond to recent automation errors.

A behavioral claim requires human choice data collected under the matched experimental design.

