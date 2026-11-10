# Location-scale moderator analysis of psychological interventions for suicidality

Analysis code for:

> Ma, C., von Spreckelsen, P., Harrer, M., Kuper, P., van Straten, A., & van Ballegooijen, W.
> *Heterogeneity of Treatment Effects in Psychological Interventions for Suicidality:
> A Meta-Epidemiological Study of Location and Scale Moderators.* Submitted to the
> *Journal of Affective Disorders*.

Preregistration: OSF, <https://doi.org/10.17605/OSF.IO/XEMVT>

## Contents

| File | Description |
|---|---|
| `suicide_intervention_lsm_metaanalysis.Rmd` | Complete analysis: data preparation, effect sizes, publication bias, univariate location-scale models, multi-model selection, sensitivity analyses, supplementary and main-text figures |
| `renv.lock`, `.Rprofile`, `renv/` | Package environment (renv) |
| `CITATION.cff` | Citation metadata (read by GitHub and Zenodo) |
| `LICENSE` | MIT licence for the code |

## Data

The analysis uses the Metapsy database *Suicide Prevention: Psychological
Interventions vs. Control* (van Ballegooijen & Harrer, 2025;
<https://doi.org/10.5281/zenodo.8364508>; <https://www.metapsy.org>).
Save the dataset as `master.xlsx` in the same folder as the `.Rmd` file.

## How to run

The R package environment is managed with [renv](https://rstudio.github.io/renv/).

1. Install R (≥ 4.4).
2. Open this folder in RStudio (or start R in this folder). renv activates
   automatically via `.Rprofile`.
3. Restore the exact package versions recorded in `renv.lock`:
   ```r
   install.packages("renv")   # if not yet installed
   renv::restore()
   ```
4. Put `master.xlsx` next to the `.Rmd` file.
5. Knit `suicide_intervention_lsm_metaanalysis.Rmd`, or run
   `rmarkdown::render("suicide_intervention_lsm_metaanalysis.Rmd")`.

The full run takes some time, mainly because of the permutation tests (1,000
permutations per flagged moderator) and the repeated multi-model selections.
Chunks are cached (`*_cache/` folder), so later knits only rerun what changed;
delete the cache folder to force a complete rerun.

## Scope

The script reproduces the main analyses reported in the article (publication
bias, univariate location-scale models, multi-model selection, and the RoB,
influential-case and outlier sensitivity analyses, including Figures 2 and 3).
A few supplementary checks were computed separately and are not part of this
script: pooled estimates and prediction intervals after excluding influential
studies or outliers, the missingness comparison (Tables S22–S23), the
cluster-robust and one-comparison-per-study analyses (Table S24), and
convergence rates by moderator.

## Outputs

Written to the working directory:

- `ideation_data.rda`, `attempt_data.rda` (and `.xlsx`): analytic datasets
- `publication_bias_results.rda`, `univariate_results.rda`, `multimodel_results.rda`,
  `sensitivity_rob_results.rda`, `sensitivity_influence_outlier_results.rda`: fitted models
- `*.csv`: coefficient tables, top-10 model tables, publication-bias summary
- `figures_main/`: Figures 2 and 3 (PDF, EPS, TIFF)

## Licence

Code: MIT (see `LICENSE`). The data are subject to the licence of the Metapsy database.

## Contact

Chenchao Ma, Amsterdam UMC / Vrije Universiteit Amsterdam
