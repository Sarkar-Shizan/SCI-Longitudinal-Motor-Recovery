# Explainable Landmark-Based Prediction of Motor Outcomes After Traumatic Spinal Cord Injury

**Research code and aggregate analysis artifacts** for retrospective landmark-based prediction of nominal Week-26 total motor score in the Sygen SCI cohort.

> **Research use only.** This repository is not a clinical decision-support system. It does not establish prospective usefulness, external validation, or confirmed independent test-set generalization.

## Study overview

From 791 source records, 659 patients had an observed nominal Week-26 total motor score. The patient-disjoint partition used 461 training, 99 validation, and 99 internal-test patients. Four cumulative predictor sets were evaluated: baseline, nominal Week 4, Week 8, and Week 16.

In the principal matched validation comparison, MAE decreased from 14.08 at baseline to 9.98, 6.44, and 4.85 at subsequent landmarks. A separately optimized B16 LightGBM estimator achieved internal-test MAE 5.54, RMSE 10.30, and R² 0.880. These are **distinct fitted evaluation procedures**; estimates should not be pooled or presented as independent repeated evaluations. Later landmarks both introduced neurological information and shortened the remaining prediction horizon.

## Contents

```text
notebooks/
  01_SCI_Recovery_Full_Analysis.ipynb
  02_Archived_Model_Inference_Reproduction.ipynb
data/README.md
results/tables/
results/figures/
reproducibility/
docs/
requirements.txt
environment.yml
.gitignore
```

The main notebook is an **archived research notebook**, not a guaranteed portable one-command pipeline. It was written for the researcher's original Kaggle and project directory layout. Source code is retained, but cached outputs and execution history were cleared before release. The second notebook checks archived-model inference and requires inputs that are intentionally not bundled.

## Setup (inspection / authorized reproduction)

Using Python 3.13 and a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows PowerShell: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter lab
```

You may need to install Jupyter separately (`pip install jupyterlab`) and update original Kaggle paths before executing notebook cells. **Do not run the main notebook without reviewing its file operations and required paths.** The data necessary for model rebuilding are not included; see [`data/README.md`](data/README.md).

## Research outputs

- `results/tables/`: selected **aggregate** cohort summaries, landmark comparisons, CV summaries, and uncertainty summaries.
- `results/figures/`: selected population-level figures, benchmark comparisons, and model diagnostics. Individual patient-level explanation figures and patient-specific output tables are excluded.
- `reproducibility/archived_inference_audit_summary.json`: report of stored-model inference reproduction; not a complete retraining audit.
- `docs/MODEL_CARD.md`: archived model notes; review in conjunction with `docs/RESEARCH_LIMITATIONS.md`.

The notebooks and aggregate outputs have not been independently rerun in this publication package. For the full methodological limitations see [`docs/RESEARCH_LIMITATIONS.md`](docs/RESEARCH_LIMITATIONS.md).

## Data sharing and privacy

This repository **does not include raw/processed Sygen patient data, PTID lists, frozen test arrays, original predictions or saved model pickles**. Consult the source *SCI Neurological Recovery* repository and responsible data custodians about access terms. We have not verified permission to redistribute clinical patient-level records.

## Manuscript / citation

**Manuscript title:** *Explainable Landmark-Based Prediction of Motor Outcomes After Traumatic Spinal Cord Injury Using Longitudinal Neurological Assessments*.

Authors, DOI, publication venue, ethics information, code license and release date should be completed by the author using verified information before public release. This repository is an associated research artifact and is not evidence of clinical validation.
