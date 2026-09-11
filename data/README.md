# Data provenance

`raw/jtpa.raw` is the unmodified public research extract for Abadie, Angrist,
and Imbens (2002), *Instrumental Variables Estimates of the Effect of
Subsidized Training on the Quantiles of Trainee Earnings*, Econometrica 70(1), 91–117.

- [MIT data archive](https://economics.mit.edu/people/faculty/josh-angrist/angrist-data-archive)
- [Exact data download](https://economics.mit.edu/sites/default/files/publications/jtpa.raw)
- [Authors' column mappings](https://economics.mit.edu/sites/default/files/inline-files/qeffectsfinal.m)
- [Study paper](https://economics.mit.edu/sites/default/files/publications/Instrumental%20Variables%20Estimates%20of%20the%20Effect%20of.pdf)
- [Full public-use archive and codebooks](https://www.upjohn.org/data-tools/employment-research-data-center/national-jtpa-study)

Retrieved 2026-09-09. SHA-256: `a662edacf90cc2d1298504c5e527c2289974be4eca01a6ea2075cca210dfdb4a`.
The extract has 11,204 records and 19 whitespace-separated columns without a header.
MIT permits teaching and research use with attribution; cite the study and archive in your write-up.

## Reading this extract

The starter dictionary in `../docs/data_dictionary.csv` follows the column positions
in the authors' MATLAB code. The first five columns receive descriptive names;
remaining covariate names preserve the authors' labels. The study defines the
outcome, assignment, and enrollment variables. Fields needing further codebook
review are explicitly marked; the dictionary is not a substitute for the full codebook.

This is prepared research data. The name `raw/` means we preserve the downloaded
bytes, not that the data are untouched survey responses. `hsorged`, `married`,
and `wkless13` include fractional entries. Do not round them, cast them to bool,
or treat every nonzero value as 1. Investigate their preparation before deciding
how to use them for exact matching. Absence of nulls here does not establish
absence of missingness in the underlying study.

Do not assume every field in the replication covariate list is an appropriate
baseline control for your estimand. Verify service-strategy and survey indicators,
including their timing. The extract has age-band indicators rather than exact age;
do not assume an all-zero age pattern means a missing age.

Keep the source file unchanged. Save any derived analysis files under `processed/`.
