Trustworthy Cardiovascular Prediction with Quantitative Explainability Evaluation

This repository contains the reproducibility code and supporting files for the study:

Trustworthy Cardiovascular Prediction with Quantitative Explainability Evaluation

Overview

The study develops and evaluates a calibrated and explainable machine-learning framework for cardiovascular disease prediction and ordered risk stratification.

The workflow includes:

Dataset A: binary cardiovascular disease prediction

nine baseline machine-learning models

calibrated HistGradientBoosting (HGB)

calibrated Explainable Boosting Machine (EBM)

weighted HGB-EBM hybrid prediction

SHAP and intrinsic EBM explanation analysis

quantitative explanation agreement

explanation-space stability

feature-space fidelity

feature-space stability

age-stratified robustness

Dataset B: leakage-controlled LOW / INTERMEDIARY / HIGH cardiovascular risk stratification

strict 5-fold cross-fitted evaluation

cross-fitted isotonic calibration

HIGH-risk SHAP analysis

cross-dataset explanation concordance across nine harmonized clinical concepts

Main Reproducibility Notebook

The primary notebook is:

CVD_Q1_Final_GitHub_Master_Notebook.ipynb

It contains the final frozen workflow and manuscript-level values used in the paper.

Repository Structure

trustworthy-cvd-xai/
│
├── CVD_Q1_Final_GitHub_Master_Notebook.ipynb
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── README.md
│
└── outputs/
    └── README.md

Data

This repository does not redistribute the raw datasets unless their original licenses explicitly permit redistribution.

Place the required datasets locally under:

data/
├── cardio_train.csv
└── CVD Dataset.csv

Dataset A is used for binary CVD prediction.

Dataset B is used for ordered cardiovascular risk stratification.

Important: Dataset B is not treated as external validation of Dataset A because the datasets represent different endpoints, feature structures, and modelling objectives.

Environment

Recommended Python version:

Python 3.10+

Install dependencies with:

pip install -r requirements.txt

Running the Notebook

Clone or download this repository.

Place the required datasets under the data/ folder.

Install the required Python packages.

Open CVD_Q1_Final_GitHub_Master_Notebook.ipynb.

Run the notebook sequentially from top to bottom.

Generated result tables are written to the outputs/ directory.

Main Model Definitions

Dataset A

The final binary framework combines calibrated HGB and EBM probabilities:

[
P(CVD) = 0.75P_{HGB} + 0.25P_{EBM}
]

The framework evaluates both prediction quality and quantitative explanation reliability.

Dataset B

The final primary risk-stratification model is:

Nominal Random Forest + cross-fitted isotonic calibration

Ordinal XGBoost and EBM are retained as comparison models.

Explainability Evaluation

Explanation quality is evaluated using multiple complementary measures rather than relying only on feature-importance plots.

The study includes:

global Spearman and Kendall rank agreement

Top-k overlap

patient-level Spearman agreement

cosine similarity

attribution-sign agreement

explanation-space stability

perturbation-based feature-space fidelity

feature-space stability

age subgroup robustness

cross-dataset rank concordance

Main Interpretation

The central study finding is:

Strong within-dataset explanation reliability does not imply cross-dataset explanation transferability.

Cross-dataset explanation analysis is therefore interpreted as a test of explanatory consistency rather than predictive external validation.

Important Interpretation Boundaries

Model outputs are cardiovascular predictions or risk estimates, not diagnoses.

SHAP and EBM attributions describe learned model behaviour and should not be interpreted as causal effects.

Dataset B is not an external validation dataset for Dataset A.

The repository does not claim clinical deployment readiness.

Final Dataset-B results come from strict cross-fitted evaluation.

Corrected feature-space fidelity results use consistent random-comparator definitions.

Reproducibility Notes

The final notebook consolidates the validated outputs from the study's development phases, including:

baseline model comparison

calibration

hybrid prediction

explanation extraction

explanation agreement and stability

corrected feature-space fidelity

subgroup robustness

strict Model-B cross-fitted calibration

cross-dataset explanation concordance

reviewer-defence statistical inference

Citation

If this work is accepted or published, please cite the corresponding paper.

A formal citation will be added here after publication.
