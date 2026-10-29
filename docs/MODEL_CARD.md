# SCI Dynamic Recovery Prediction Model Card

## 1. Model Overview

**Model name:** Optimized LightGBM

**Dataset:** Sygen Spinal Cord Injury Dataset

**Prediction target:** 26-week total motor score

**Prediction landmark:** Week 16

**Model type:** Supervised machine-learning regression

**Framework:** LightGBM

**Documentation date:** 2026-10-28

---

## 2. Research Objective

The objective of this research is to develop and
internally validate an explainable machine-learning
model for predicting 26-week neurological motor
outcomes following spinal cord injury.

The research investigates whether longitudinal
neurological assessments improve prediction
compared with baseline clinical information.

The model estimates future motor scores rather
than directly estimating causal treatment effects.

---

## 3. Dataset and Study Population

Dataset: Sygen Spinal Cord Injury Dataset

Initial records: 791

Analytical patients: 659

Excluded records: 132

Training patients: 461

Validation patients: 99

Held-out test patients: 99

Patient-level splitting was assessed using
PTID-based overlap analysis.

Previously saved audit results reported zero
overlapping PTIDs between training, validation
and test cohorts.

The precise reasons for cohort exclusions must
be confirmed using the cohort derivation audit.

---

## 4. Prediction Target

The primary outcome is the total neurological
motor score measured at Week 26 following
spinal cord injury.

The final dynamic model uses information
available through the Week-16 landmark.

The model should not be described as making
Week-16-informed predictions at admission.

---

## 5. Candidate Clinical Predictors

The research investigates predictors including:

- Age
- Sex
- AIS grade
- Baseline motor score
- Week-4 motor change
- Week-8 motor change
- Week-16 motor change

The exact final model input columns and their
order must match the saved feature manifest.

Predictor availability must be checked to
ensure that no post-landmark information
enters earlier prediction models.

---

## 6. Model Development

Primary model:

Optimized LightGBM

The research workflow includes:

- Training, validation and test data splitting
- Feature engineering
- Missing-value processing
- Hyperparameter optimization
- Nested cross-validation
- Repeated cross-validation
- Longitudinal landmark comparisons

All preprocessing and tuning procedures
must be verified for fold-level isolation.

---

## 7. Reported Predictive Performance

Final internal test cohort:

R-squared: 0.8800

Mean absolute error: 5.54

Root mean squared error: 10.30

These values are historical results reported
by the existing research notebook.

They are not independently reproduced
by the model-card generation step.

The final manuscript should include
uncertainty intervals where appropriate.

---

## 8. Longitudinal Prediction

The research evaluates four assessment landmarks:

- Baseline
- Week 4
- Week 8
- Week 16

The objective is to assess whether updated
clinical assessments provide additional
predictive information.

Fixed-algorithm landmark ablation is preferred
when quantifying the incremental value of
longitudinal information.

Comparisons must use the same evaluation
patients and appropriately matched outcomes.

---

## 9. Explainability

The research includes:

- SHAP feature importance
- SHAP interpretation
- Permutation feature importance

These methods describe associations between
model features and model predictions.

They do not establish causal relationships
between predictors and neurological recovery.

---

## 10. Prediction Uncertainty

The research includes conformal prediction
interval estimation.

Previously reported nominal 95% prediction
intervals covered approximately 90.91%
of the held-out test observations.

This empirical coverage does not demonstrate
that 95% coverage was achieved.

Formal conformal coverage claims require
verification that calibration observations
were not used improperly for model selection
or other adaptive decisions.

---

## 11. Missing Data

The research includes:

- Missingness analysis
- Imputation sensitivity analysis
- Week-16 missing-assessment sensitivity

The Week-16 missing-assessment subgroup
was small, limiting the reliability of
subgroup-specific conclusions.

Imputation procedures must be fitted
using only the appropriate training folds.

---

## 12. Internal Validation

The research reports:

- Nested cross-validation
- Repeated cross-validation
- Held-out test evaluation
- Bootstrap uncertainty analysis
- Learning curve analysis
- Residual and calibration analyses

The independence of model selection,
cross-validation and final testing
must be verified before publication.

---

## 13. Intended Use

This model is intended for research into
predicting neurological motor outcomes
following spinal cord injury.

Potential future applications include
clinical prognostic research and
decision-support development.

The current model is not validated for
autonomous clinical decision-making.

---

## 14. Limitations

1. The model was developed and evaluated
   using a single research dataset.

2. External validation was not performed.

3. Performance may differ in other SCI
   populations or healthcare settings.

4. Some clinical subgroups have small
   sample sizes.

5. Missing longitudinal assessments
   may affect predictive accuracy.

6. Nominal prediction interval coverage
   was not fully achieved empirically.

7. Baseline and dynamic model comparisons
   require consistent cohort evaluation.

8. The final test results have already
   been inspected during research
   development.

9. Predictive associations should not
   be interpreted as causal effects.

---

## 15. Reproducibility

Python version: 3.13.15

Platform: Linux-6.18.55+-x86_64-with-glibc2.39

Environment files:

- requirements.txt
- environment.yml
- environment_info.json

Research reproducibility additionally requires:

- Fixed data splits
- Recorded random seeds
- Saved model artifacts
- Feature order verification
- Dataset integrity verification
- Reproduction of saved predictions
- Independent environment execution

Generating environment documentation
does not establish that the entire
pipeline is reproducible.

---

## 16. Reporting Framework

The manuscript should be prepared
in accordance with TRIPOD+AI reporting
recommendations for clinical prediction
model development and validation.

A completed reporting checklist should
accompany the manuscript when required
by the target journal.

---

## 17. Clinical Deployment Status

Status: Research model only.

External validation: Not performed.

Prospective validation: Not performed.

Clinical deployment authorization:
Not established.

The model should not be used as the
sole basis for patient treatment or
prognostic decisions.
