# Fixed Hold-Out versus Out-of-Fold Meta-Learning for Deep Stacking

## Matched Cross-Domain Evaluation

This repository accompanies the manuscript submitted to *Neural Computing and Applications*.

**Manuscript number:** NCAA-D-26-04254

## Overview

This study compares fixed hold-out probability stacking with five-fold
out-of-fold (OOF) stacking across two image-classification domains:

- **CIFAR-10:** four base-model architectures.
- **Binary SARS-CoV-2 CT classification:** ResNet50 and EfficientNetB0.

Logistic Regression and LightGBM are evaluated as meta-learners, with
soft voting as a non-learned baseline.

The study also reports uncertainty estimates, statistical comparisons,
calibration analysis, meta-learner stability, matched meta-training-size
experiments, and repeated hold-out sensitivity analyses.

## Main reported accuracy results

| Domain | Method | Accuracy |
|---|---|---:|
| CIFAR-10 | Soft voting | 91.47% |
| CIFAR-10 | Hold-out Logistic Regression | 91.63% |
| CIFAR-10 | Hold-out LightGBM | 91.31% |
| CIFAR-10 | OOF Logistic Regression | 91.85% |
| CIFAR-10 | OOF LightGBM | 91.98% |
| CT | Soft voting | 95.98% |
| CT | Hold-out Logistic Regression | 96.18% |
| CT | Hold-out LightGBM | 95.77% |
| CT | OOF Logistic Regression | 96.38% |
| CT | OOF LightGBM | 96.58% |

These values are the manuscript's reported results. Consult the result
tables for uncertainty estimates and statistical comparisons.

## Repository structure

```text
.
├── README.md
├── notebooks/
│   ├── Paper_1_CIFAR10_Matched_Holdout_vs_OOF_FINAL.ipynb
│   ├── Paper_1_Combined_Results_and_Statistics.ipynb
│   ├── Paper_1_Matched_Holdout_vs_OOF_Stacking_CLEANED.ipynb
│   └── Paper_3_Protocol_Sensitivity_Extended_Experiments.ipynb
├── results/
│   ├── primary/
│   ├── matched_size/
│   └── repeated_holdout/
└── docs/
    ├── FILE_MANIFEST.csv
    ├── REPRODUCIBILITY.md
    └── DATA_AND_CODE_AVAILABILITY.md
```

## Results-first use

The CSV files in `results/` provide the saved numerical results without
requiring model training. They can be opened with spreadsheet software
or loaded using pandas.

Example:

```python
import pandas as pd

results = pd.read_csv(
    "results/primary/Paper1_Combined_Matched_Results.csv"
)
print(results.head())
```

## Running the notebooks

The notebooks document the experimental workflow. Full execution may
require the original datasets, saved base-model probabilities, split
indices, and other intermediate files. Some cells can train models when
required saved outputs are unavailable.

Read `docs/REPRODUCIBILITY.md` before running a notebook. Do not assume
that every notebook can run from a fresh environment using this repository
alone.

## Data and limitations

The staged repository contains selected result tables and notebooks.
It does not automatically include every dataset, model checkpoint,
prediction array, or intermediate artifact used in the experiments.
Consult `docs/DATA_AND_CODE_AVAILABILITY.md` for this distinction.

The results should be interpreted in light of the experimental design,
including the limited number of seeds in repeated hold-out analysis and
the size and availability of the CT test set.

## Software

The notebooks use Python and scientific machine-learning libraries,
including NumPy, pandas, scikit-learn, TensorFlow, LightGBM, and
Matplotlib. Exact environment versions should be taken from the notebook
environment report where available.

## Integrity

`docs/FILE_MANIFEST.csv` records the staged file inventory and checksums.
Regenerate it after any intentional file changes.
