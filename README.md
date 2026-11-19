# Retail bank customer analysis

Reproducible customer segmentation and CLV analysis with a six-member workflow.

## Included files

- `course content/`: the supplied W3, W4, W6, W7, W8 and W9 lecture/lab materials.
- `data/Group_presentation.csv`: a byte-for-byte copy of the original dataset (10,000 rows, seven columns).
- `Bank_Customer_Analysis_Study_EN.Rmd`: English study edition, with course references, method explanations, six-member boundaries and a presentation plan.
- `Bank_Customer_Analysis_Submission_EN.Rmd`: English submission report explaining calculations, findings and limitations without teaching/week references.
- `Bank_Customer_Analysis.Rproj`: portable RStudio project with automatic workspace restoration disabled.

The Chinese study edition is maintained locally and is excluded from Git. Generated HTML, result folders, local sessions and earlier drafts are also excluded. The repository is private.

## Run

1. Clone or download the repository and open `Bank_Customer_Analysis.Rproj` in RStudio.
2. If needed, install `cluster`, `knitr` and `rmarkdown` from the R Console: `install.packages(c("cluster", "knitr", "rmarkdown"))`.
3. Open either English RMD and run its chunks from top to bottom, or use Knit. RStudio supplies Pandoc for HTML rendering.
4. Data is read with the relative path `data/Group_presentation.csv`. Do not change the raw file.
5. Outputs are generated in `outputs/study_en/` or `outputs/submission/`. They are not committed.

Both notebooks run the same 57 code chunks in the same order, with separate output directories. Fixed seeds reproduce the analysis on the tested environment; review segment names and narrative numbers if data or software changes.

## Six-member division

| Member | Responsibility | Inclusive first / last chunk |
|---|---|---|
| 1 (project owner) | Data cleaning and quality | `setup` / `age-mapping` |
| 2 | Exploratory and bivariate analysis | `clv-correlations` / `young-correlation` |
| 3 | K-means and solution selection | `cluster-inputs` / `sensitivity-no-capping` |
| 4 | Final cluster profiles and interpretation | `selected-clusters` / `cluster-scatter` |
| 5 | CLV regression and evaluation | `train-validation` / `age-errors` |
| 6 | Recommendations, presentation integration, exports and checks | `profit-ranking` / `session` |

Member 3 inspects candidate profiles, selects k and runs sensitivity checks before Member 4 names and profiles the final solution. This preserves contiguous ownership without changing the agreed roles. Member 5 also owns the model-choice prose; Member 6 owns the recommendation and presentation narrative. Member 6 integrates the report and runs the complete notebook after changes. Do not edit the same blocks simultaneously without coordination.

For fresh sessions: Members 2–4 run earlier blocks first. Member 5 needs block 1 to create `raw_data`. Member 6 needs blocks 1–5. The notebooks are shared sequential analyses, not six standalone scripts.

## Interpretation

Four clusters are chosen as an explicit profile-based compromise; k=2 has the highest sampled silhouette. CLV is a label from an unknown historical formula. Validation evaluates prediction of that label, not actual future profit. Regression diagnostics show material limitations. The report proposes pilots, not guaranteed causal returns.

Course documents remain attributed to their original authors. No redistribution licence is granted for those materials.
