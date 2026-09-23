# con_pit

Task data, analysis code and computational models for **Adolescents flexibly adapt action selection based on controllability inferences**
(Raab, Goldway, Foord & Hartley, *Learning & Memory*, 2024; [DOI](https://doi.org/10.1101/lm.053901.123), [OSF project](https://osf.io/e49ua/)).

## Overview

90 participants aged 8-27 performed a probabilistic Go/No-Go learning task in controllable and uncontrollable environments.
The analyses test how action selection adapts to inferred controllability across development and fit reinforcement-learning models to the choices.

## Repository contents

| Path | Contents |
|---|---|
| `Con_pit_analysis_main.Rmd` | R Markdown analysis: regressions, model comparison and figures |
| `Con_pit_analysis_main.html` | Rendered output of the analysis |
| `computational_modeling_code/` | MATLAB reinforcement-learning models. Entry point: `Main_fitting_code.m`. Likelihood functions in `lik_functions/`, parameter recovery in `param_recovery/`. Uses the [mfit](https://github.com/sjgershman/mfit) toolbox (`mfit-master/`, with its own license). |
| `data/task_data/` | Per-participant task files (MATLAB `.mat` files and logs) |
| `data/age_cov_n90.csv` | Age, age group and gender per participant |
| `data/subDemographicStats.csv` | Sample composition |
| `data/w_trial_by_trial.csv` | Trial-by-trial data used in the R analysis |

## Requirements

- MATLAB R2023a with the Optimization Toolbox (models are fitted with `fmincon`).
- R with: `R.matlab`, `afex`, `cowplot`, `dplyr`, `emmeans`, `ggplot2`, `grid`, `gridExtra`, `lme4`, `modelbased`, `nlme`, `pander`, `psych`, `rempsyc`, `report`, `see`, `segmented`, `tidyverse`.

## Running

1. **Modeling (MATLAB):** run `computational_modeling_code/Main_fitting_code.m`.
2. **Analysis (R):** knit `Con_pit_analysis_main.Rmd`. The file paths at the top point to the data files, so adjust them to your local copy.

## Citation

Raab, H. A., Goldway, N., Foord, C., & Hartley, C. A. (2024). Adolescents flexibly adapt action selection based on controllability inferences. *Learning & Memory, 31*(3), a053901. https://doi.org/10.1101/lm.053901.123
