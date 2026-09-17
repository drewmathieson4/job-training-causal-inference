# Job Training and Income

This project tries to uncover the effect of job training on income, using data from
the National JTPA Study.

## Notebooks

1. **[Data preprocessing](notebooks/01_data_preprocessing.ipynb)**: loads and checks the raw data, recodes imputed values, and saves the processed data used by the analysis notebooks.
2. **[DAG and controls](notebooks/02_dag_and_controls.ipynb)**: proposes the causal DAG and chooses the baseline control set shared by the analysis notebooks.
3. **[IV regression](notebooks/03_iv_regression.ipynb)**: estimates the enrollment effect using randomized assignment as an instrument.
4. **[Matching](notebooks/04_matching.ipynb)**: repeats the analysis with nearest-neighbor matching on the controls, ignoring the randomized offer, as a comparison against the IV estimate.

## Headline result

Enrolling in JTPA services raises 30-month earnings by about **$1,771** (robust SE $498,
95% CI $795 to $2,746) for compliers, roughly an 11.7% increase over average 30-month
earnings of about $15,041. Randomized assignment to the program is used as an instrument
for actual enrollment.

| Model | Estimand | Estimate ($) | Robust SE ($) | 95% CI ($) |
|---|---|---:|---:|---:|
| Assignment OLS | Offer effect (ITT) | 1,159 | 330 | 512 to 1,807 |
| Enrollment OLS | Enrollment association (non-causal) | 2,791 | 320 | 2,164 to 3,418 |
| Uncontrolled IV | Enrollment effect for compliers | 1,849 | 526 | 817 to 2,881 |
| Controlled IV | Enrollment effect for compliers | 1,771 | 498 | 795 to 2,746 |

All models use the same 11,204 people. Full details, diagnostics, and limitations are in [the IV regression notebook](notebooks/03_iv_regression.ipynb).


## Links

- [MIT data archive](https://economics.mit.edu/people/faculty/josh-angrist/angrist-data-archive)
- [Exact data download](https://economics.mit.edu/sites/default/files/publications/jtpa.raw)
- [Authors' column mappings](https://economics.mit.edu/sites/default/files/inline-files/qeffectsfinal.m)
- [Study paper](https://economics.mit.edu/sites/default/files/publications/Instrumental%20Variables%20Estimates%20of%20the%20Effect%20of.pdf)
- [Full public-use archive and codebooks](https://www.upjohn.org/data-tools/employment-research-data-center/national-jtpa-study)
