# Scientific reporting and evidence status

- Cohort: 791 source patient records; 659 with observed nominal Week-26 outcome (461 training / 99 validation / 99 internal test).
- Sequential landmark accuracy is confounded with shrinking time-to-outcome; information gain at a fixed horizon was not isolated.
- Actual assessment dates and timing adherence were not verified for each patient; landmark labels are nominal.
- Historic independence of the 99-patient internal-test outcome access from subsequent research decisions could not be established.
- The 99 validation patients were reused for exploratory benchmarking, comparisons and model inspection.
- 132 source patients lacked the nominal Week-26 outcome, with potential selection bias.
- The fitted model was not externally or prospectively validated.
- Exploratory prediction intervals targeting 95% coverage contained 90 of 99 internal-test outcomes (90.9%); formal coverage guarantee was not established.
- Public code supports inspection of the archived notebook but not a proven clean-room end-to-end reproduction.

Please consult the manuscript for full methods, model comparisons and interpretations.
