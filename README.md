# Job Training Causal Inference

A chapters 1–10 capstone for *Causal Inference for the Brave and True*.

**Question:** How does enrolling in JTPA services affect subsequent earnings,
and how does accounting for selection change the answer?

## Open the notebook

Open this folder in VS Code, then open `notebooks/01_job_training_capstone.ipynb`.
Select **Python Environments → the existing causal-inference/.venv/bin/python**
as the notebook kernel if VS Code does not select it automatically.
Its full path is `/Users/drewmathieson/Projects/causal-inference/.venv/bin/python`.
The workspace's default Python interpreter points to this existing environment;
a notebook kernel may still need to be selected separately.

Run the setup and data-loading cells. They import the packages, locate the project,
verify the bundled download, attach column names, and display a small preview.
The remaining cells contain prompts and empty work areas for your analysis.
No treatment effects or solutions are filled in.

You can also launch JupyterLab from this project's directory:

```bash
../causal-inference/.venv/bin/python -m jupyterlab
```

## Layout

```text
notebooks/01_job_training_capstone.ipynb  Setup, loader, and exercises
data/raw/jtpa.raw                       Original MIT download; read only
data/processed/                         Your derived datasets
docs/data_dictionary.csv                Column order, descriptions, and review notes
data/README.md                         Provenance and data preparation caveats
outputs/figures/                        Your exported figures
requirements.txt                       Verified direct dependency versions
```

## Packages

- pandas and NumPy: loading, cleaning, and numerical calculations.
- SciPy: statistical calculations and uncertainty.
- Matplotlib and seaborn: exploratory plots.
- statsmodels: OLS, WLS, formulas, interactions, and robust standard errors.
- linearmodels: IV2SLS and its first-stage diagnostics and inference.
- scikit-learn: scaling and nearest-neighbor matching tools.
- graphviz: DAGs; rendering also requires the system `dot` executable,
  already available in the current causal-inference setup.
- JupyterLab, ipykernel, and nbformat: notebook execution and format support.

## Optional standalone environment

The project initially shares the existing learning environment. To give it a
separate environment later, run from this folder:

```bash
python3.14 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
```

Then change `python.defaultInterpreterPath` in `.vscode/settings.json` to
`${workspaceFolder}/.venv/bin/python` and select that notebook kernel.
The requirements pin the direct packages verified in the current environment;
they are not a complete transitive dependency lockfile.

## Suggested deliverable

One completed notebook and a two-page write-up: your question and DAG, EDA,
estimates and uncertainty, assumptions, limitations, and interpretation of differences
across estimands. Start with total 30-month earnings and at most one subgroup comparison.
Data sources and attribution are in `data/README.md`.
