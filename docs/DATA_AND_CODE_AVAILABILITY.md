# Data and Code Availability

## Code

The repository provides selected Jupyter notebooks documenting the
matched hold-out versus five-fold out-of-fold stacking experiments and
the associated statistical and sensitivity analyses.

The notebooks include environment-specific paths and may depend on
intermediate files that are not distributed in this repository. They
should not be assumed to execute end-to-end in a fresh environment
without configuration.

## Results

Selected primary results, matched meta-training-size results, and
repeated hold-out summaries are supplied as CSV files under `results/`.
These files allow inspection of the reported numerical results without
rerunning model training.

## Data and intermediate artifacts

The staged package does not include the complete CT dataset, all
intermediate probability arrays, all split-index files, or every model
checkpoint. Access to these materials may be required for full
reproduction of the experiments.

Before public release, confirm that any proposed dataset or intermediate
artifact can legally and ethically be redistributed. Do not publish
private, restricted, or unlicensed data.

## Reproducibility statement

The availability of result tables supports inspection of the reported
findings, but does not by itself constitute an independent reproduction
of the complete experimental pipeline.
