# AI-Driven QSAR and Molecular Modeling of δ-Opioid Receptor Ligands

A reproducible computational research portfolio accompanying the published study:

**Fakhar Z. et al. (2024). _Revealing key structural features for developing new agonists targeting δ opioid receptor: Combined machine learning and molecular modeling perspective._ Medicine in Drug Discovery.**

## Project overview

This repository demonstrates an end-to-end computational workflow for molecular activity prediction against the δ-opioid receptor (DOR), integrating molecular descriptor preparation, feature selection, machine learning, and model evaluation.

```text
Descriptor data
      ↓
01 — Descriptor Matrix Preparation
      ↓
all_descs.csv
      ↓
02 — AI-Driven QSAR
      ↓
K-best feature selection
      ↓
Random Forest + XGBoost
      ↓
5-fold cross-validation
      ↓
Held-out test evaluation
      ↓
Prediction and residual analysis
```

## Repository structure

```text
DOR_AI_QSAR_GitHub_Portfolio/
├── README.md
├── requirements.txt
├── notebooks/
│   ├── 01_Descriptor_Matrix_Preparation_GitHub.ipynb
│   └── 02_DOR_AI_QSAR_GitHub_Implementation.ipynb
├── data/
│   └── README.md
├── results/
│   └── README.md
└── figures/
    └── README.md
```

## Notebook 01 — Descriptor Matrix Preparation

This notebook prepares the descriptor matrix used by the downstream QSAR workflow. It loads descriptor blocks, checks identifiers and target variables, removes duplicated identifier/target fields where appropriate, combines descriptor blocks, performs quality-control checks, and exports the resulting descriptor matrix as `all_descs.csv`.

Only data that are legally and ethically appropriate to redistribute should be included in the public repository.

## Notebook 02 — AI-Driven QSAR

The second notebook implements the machine-learning component of the workflow:

- molecular descriptor-based representation;
- mutual-information feature selection using `SelectKBest`;
- Random Forest regression;
- XGBoost regression;
- 5-fold cross-validation;
- independent held-out test evaluation;
- R², RMSE and MAE;
- experimental-versus-predicted activity plots;
- residual analysis.

### Methodological note

Supervised feature selection is performed **after the train/test split** and is fitted only on the training data. This prevents information from the held-out test set from influencing descriptor selection.

## Data

The original research used molecular activity data and multiple descriptor families. The public repository should not contain proprietary, confidential, unpublished, or restricted data.

If the dataset cannot be redistributed, provide instructions in `data/README.md` describing its source, curation, expected file name and column structure, and how an authorized researcher can obtain it.

## Reproducibility

Create a Python environment:

```bash
python -m venv .venv
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebooks in order:

```text
01_Descriptor_Matrix_Preparation_GitHub.ipynb
02_DOR_AI_QSAR_GitHub_Implementation.ipynb
```

The QSAR notebook expects:

```text
data/all_descs.csv
```

## Scientific interpretation

The workflow demonstrates:

**chemical representation → feature selection → machine learning → validation → interpretation**

Future extensions may include scaffold-based splitting, chemically independent external validation, applicability-domain analysis, SHAP interpretation, molecular fingerprints, hybrid representations, molecular docking, molecular dynamics-derived features, and AI-guided molecular design.

## Relationship to the published research

This repository is a **public, cleaned implementation inspired by the computational methodology reported in the published study**. It should not be presented as an exact reproduction of the published numerical results unless the original dataset, preprocessing, software versions, random seeds, and modeling parameters are reproduced exactly.

## Citation

Fakhar Z. et al. *Revealing key structural features for developing new agonists targeting δ opioid receptor: Combined machine learning and molecular modeling perspective.* *Medicine in Drug Discovery*. 2024.

Please also cite the original software packages and databases used in derivative analyses.

## Author

**Dr. Zeynab Fakhar, Ph.D.**

Pharmaceutical Chemistry · Computational Drug Discovery · Molecular Modeling · QSAR · Machine Learning · Cheminformatics
