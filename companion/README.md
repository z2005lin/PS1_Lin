# PS1 Technical Companion

This directory contains the technical and reproducibility materials for the PS1 project:

**When Should Humans Take Over? Recent Errors and Authority under Imperfect Automation**

The project studies whether recent automation error history changes human takeover decisions when current automation reliability, failure loss, and takeover cost remain fixed.

## Project Materials

The main project materials in this directory are organized as follows:

```text
companion/
├── hf_space/
│   ├── index.html
│   └── README.md
├── notebooks/
│   └── takeover_boundary_analysis.ipynb
├── outputs/
│   ├── economic_boundary.png
│   └── synthetic_takeover_boundaries.png
├── README.md
└── requirements.txt
```

The repository template also contains supporting development files and directories such as `src/`, `tests/`, and `requirements-dev.txt`. They are retained from the course template and are not part of the main computational analysis described below.

## Google Colab Notebook

The main computational notebook is:

`notebooks/takeover_boundary_analysis.ipynb`

Google Colab:

https://colab.research.google.com/drive/1mM6bZV-yfjKA-C0pycUg5f_y0gOGNzTO?usp=sharing

The notebook implements the computational analysis used in the proposal. It:

1. defines the expected-cost decision model;
2. derives the economic takeover boundary;
3. constructs matched Error and No Error scenarios;
4. visualizes the economic benchmark;
5. generates synthetic choices for a computational check;
6. estimates Error and No Error takeover boundaries using logistic regression;
7. compares the history effect at different distances from the economic boundary.

The expected cost of continued automation is:

`EC_auto = (1 - p)L`

The cost of takeover is:

`EC_takeover = C`

The economic takeover boundary is:

`p* = 1 - C/L`

With `L = 100` and `C = 20`, the notebook uses:

`p* = 0.80`

The main comparison estimates separate takeover boundaries for the Error and No Error conditions and calculates:

`Delta p = p_hat_Error - p_hat_NoError`

## Dependencies

The notebook requires:

- NumPy
- pandas
- Matplotlib
- scikit-learn

The required packages are recorded in `requirements.txt`.

Google Colab normally provides these packages by default. For local execution, install the dependencies with:

```bash
pip install -r requirements.txt
```

## Reproduction Instructions

The computational analysis uses a fixed random seed of `206`.

To reproduce the analysis:

1. Open the Google Colab link above.
2. Select **Runtime → Restart session and run all**.
3. Run all notebook cells from the beginning.
4. Confirm that the notebook completes without execution errors.
5. Inspect the generated scenario tables, boundary estimates, and figures.

No external dataset is required. Matched scenarios and synthetic behavioral choices are generated directly in the notebook.

## Actual Computational Outputs

The `outputs/` directory contains two figures generated from the computational analysis.

### `economic_boundary.png`

This figure shows the expected-cost takeover boundary at `p* = 0.80`.

Reliability below the boundary favors **Take Over** under expected-cost minimization, while reliability above the boundary favors **Keep Auto**.

### `synthetic_takeover_boundaries.png`

This figure shows the fitted takeover probabilities for the Error and No Error conditions in the synthetic computational check.

The notebook also produces actual cell outputs including:

- the matched scenario table;
- synthetic choice summaries;
- logistic regression estimates;
- estimated Error and No Error takeover boundaries;
- the estimated synthetic boundary shift.

## Evidence Status and Limitations

The economic boundary is a derived result from the expected-cost model. The tables, estimates, and figures are actual computational outputs produced by the notebook.

The behavioral choices used in the boundary analysis are synthetic. They are generated from an assumed probability model only to verify that the computational procedure can recover an imposed recent-error effect.

The synthetic results therefore do not establish that real people change their takeover behavior after an automation error. Testing this behavioral claim requires human choice data collected under matched Error and No Error conditions while current reliability, failure loss, and takeover cost remain fixed.

## Hugging Face Interactive Demo

The `hf_space/` directory contains the source files for the interactive **Trust or Take Over?** demo:

- `hf_space/index.html` contains the interactive interface and game logic.
- `hf_space/README.md` contains the Hugging Face Space configuration and documentation.

Live demo:

https://huggingface.co/spaces/dku-comsci-econ206-2026/TrustOrTakeOver

The demo presents the same takeover problem in an interactive form. Players observe current reliability, failure loss, takeover cost, and recent history before choosing **Keep Auto** or **Take Over**.

Benchmark information and decision analysis are hidden during play and shown only after all decisions are completed.

The interactive demo uses a smaller scenario set for presentation, while the Colab notebook uses a denser reliability grid around the economic boundary for computational analysis.

## Reproducibility Record

- Main notebook: `notebooks/takeover_boundary_analysis.ipynb`
- Environment: Google Colab
- Random seed: `206`
- Dependencies: `requirements.txt`
- Computational outputs: `outputs/`
- Interactive demo source: `hf_space/`
- GitHub repository: https://github.com/z2005lin/PS1_Lin
- Submitted commit: `[FINAL COMMIT HASH]`

For the final fresh-run check, the Colab runtime was restarted and all notebook cells were executed sequentially from the beginning without external data or manual intermediate inputs.
