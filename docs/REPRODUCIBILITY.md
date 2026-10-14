# Reproducibility Guide

## 1. Two ways to use this repository

### A. Inspect the reported results

This is the recommended starting point. Load the CSV files in `results/`
without executing training cells.

Primary results include:

- Combined matched-protocol results
- Bootstrap confidence intervals
- Calibration results
- McNemar test results
- Meta-learner seed-level results
- Original full-size and matched-size tables
- Hold-out versus OOF differences

Additional files cover matched meta-training sizes and repeated hold-out
experiments.

### B. Re-run experiments

A full rerun is a separate task and may require data and intermediate
artifacts that are not distributed here. Review all paths and prerequisites
before running cells.

## 2. Recommended notebook order

1. `Paper_1_Matched_Holdout_vs_OOF_Stacking_CLEANED.ipynb`
   - CT matched-protocol workflow.
   - May train missing hold-out base-model predictions.
2. `Paper_1_CIFAR10_Matched_Holdout_vs_OOF_FINAL.ipynb`
   - CIFAR-10 matched-protocol workflow.
3. `Paper_1_Combined_Results_and_Statistics.ipynb`
   - Consolidation and statistical analyses.
4. `Paper_3_Protocol_Sensitivity_Extended_Experiments.ipynb`
   - Extended sensitivity analyses; inspect prerequisites carefully.

This is a suggested inspection order, not a guarantee that every notebook
can execute from a clean runtime.

## 3. Before executing any notebook

- Review its introductory Markdown and path-configuration cells.
- Confirm that the required dataset and intermediate files exist.
- Confirm that the saved predictions correspond to the intended split.
- Check the required package versions and hardware requirements.
- Inspect cells that train models or write output files.
- Avoid executing training cells merely to inspect the published CSVs.

The notebooks currently contain environment-specific Google Drive paths.
Those paths must be configured for the user's own environment before
execution. A Drive path from the original experiment is not available to
another researcher automatically.

## 4. Interpretation and reproducibility limitations

- Saved CSV results are distinct from independently reproducing the
  underlying experiments.
- The CT dataset and intermediate arrays are not included merely because
  their paths appear in a notebook.
- The repeated hold-out analysis uses three independent seeds, as reported
  in the manuscript.
- Check the matched-size and sensitivity-analysis configurations before
  comparing their numbers with the primary results.
- Do not describe an experiment as independently reproduced unless it has
  actually been rerun and its outputs verified.

## 5. Integrity checks

Use `docs/FILE_MANIFEST.csv` to inspect the staged file inventory and
SHA-256 hashes. If repository files change, regenerate the manifest and
verify the final published files.
