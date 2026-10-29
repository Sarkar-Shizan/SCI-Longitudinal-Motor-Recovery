# Explainable Landmark-Based Prediction of Motor Outcomes After Traumatic Spinal Cord Injury

Research code and aggregate analysis artifacts for retrospective prediction of nominal Week-26 total motor score in the Sygen spinal cord injury cohort.

**Research use only.** This project is not a clinical decision-support system. It does not establish prospective usefulness, external validation, or confirmed independent test-set generalization.

## Study overview

The project evaluates longitudinal clinical prediction at baseline and Weeks 4, 8, and 16, with Week-26 total motor score as the target. The final reported model is an optimized LightGBM regressor using information available through Week 16. The project includes nested and repeated cross-validation summaries, landmark comparisons, bootstrap analyses, calibration/error analyses, and SHAP-based explainability artifacts.

The supplied project documentation reports 659 analytical patients, split into 461 training, 99 validation, and 99 internal-test patients. Reported internal-test performance is MAE 5.54, RMSE 10.30, and R² 0.880. These are historical project results; this repository packaging step does not independently retrain the model or re-verify these metrics.

## Repository layout

```text
SCI-Longitudinal-Motor-Recovery-Updated/
├── data/README.md
├── docs/
│   ├── MODEL_CARD.md
│   └── PROJECT_SUMMARY.txt
├── notebooks/01_SCI_Recovery_Full_Analysis.ipynb
├── reproducibility/
│   ├── FINAL_STATUS.json
│   └── README.md
├── results/
│   ├── figures/       # aggregate figures
│   └── tables/        # aggregate tables and reporting artifacts
├── CITATION.cff
├── LICENSE_NOTICE.md
├── environment.yml
├── requirements.txt
└── README.md
```

## Reproducibility

The notebook is provided as research code, not as a guaranteed one-command pipeline. The notebook's saved cell outputs were cleared before packaging. Running it may require an authorized copy of the dataset, changes to local file paths, and a compatible environment. See `requirements.txt` and `environment.yml`.

The repository preserves aggregate results and documentation but deliberately excludes raw and derived patient-level datasets, individual prediction exports, frozen test arrays, patient-level identifiers, and serialized model files. This is a repository-safety choice, not a claim that every upstream artifact is non-sensitive.

## Interpretation and limitations

- The target is nominal Week-26 total motor score; the final dynamic predictor set uses information through Week 16.
- Internal test performance, nested cross-validation, repeated cross-validation, and matched landmark validation are different evaluation procedures and must not be pooled or substituted for one another.
- Later landmarks provide more recent neurological information and shorten the remaining prediction horizon; landmark comparisons do not alone isolate the incremental value of longitudinal information.
- The independence of the internal test set from all historical model-selection decisions is not established by partition separation alone.
- External and prospective validation have not been performed.
- SHAP and feature-importance analyses describe model associations, not causal effects.
- The model is not validated for autonomous clinical decision-making.

## How to cite

See `CITATION.cff` for repository citation metadata. Update author and repository URL fields before publishing to GitHub.
