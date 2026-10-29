# Reproducibility notes

The aggregate files in `results/` are exported project artifacts. This repository packaging step does not rerun training, regenerate predictions, or independently verify historical metrics.

The source project records saved-model inference reproduction on a previously defined 99-patient internal test cohort, but this public repository intentionally omits frozen patient-level arrays, individual predictions, and the serialized model. The inference audit therefore cannot be independently rerun from this public package alone.

Before publication, verify the complete training pipeline in a clean environment, document all random seeds and data versions, and establish whether the internal test outcomes were inspected during model development. External validation remains necessary.
