# DataCo regional recording profiles — C3 final study
Group 67 · Ian Spikin Thomas & Juan Pablo Molina · IIB423T-1

**Assessment version:** C3-final-v1, prepared 23 November 2026 from source repository snapshot `7e9bf5f1e519fd73df0a6c502492f9ab1a09d6c6` and supplied W3 PDF. Tag this version after uploading.

**Question:** Which observed DataCo regions share recording/coverage profiles, and which comparisons of regional purchasing-intensity KPIs require further checks?

**Central message:** Before comparing regions, check how the records were captured. Three exploratory profiles are supported by the tested K-means candidates; they are not a sales ranking.

## Reading order (no setup or execution needed)
1. [W1/C1: question and EDA](notebooks/01_W1_C1.ipynb) — historical executed evidence.
2. [W2: validation and coverage](notebooks/02_W2_Validation.ipynb) — row-count audit, missingness, duplicate checks, temporal KPI, sampling and split diagnostics.
3. [C2: clustering](notebooks/03_C2_Model.ipynb) — original executed CSV analysis, model settings, baseline, silhouette, ARI and profiles.
4. [C3: visual system and decision record](notebooks/04_C3_Visual_System.ipynb) — executed final W3 redesigns, shared design rules, traceability, feedback and limitations.
5. [W3 report](evidence/W3_DataCo_Group_67.pdf) — historical redesign rationale and exploratory views.
6. [Final presentation](presentation/Group_67_C3.pptx) — external audience followed by internal reviewer.

## Source and method
DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS, v5, Constante, Silva & Pereira (2019), https://doi.org/10.17632/8gx2fvg2k6.5. Original CSV has 180,519 order-item rows, 53 variables, observed Jan 2015–Jan 2018; exclude 7,754 canceled/suspected-fraud rows after validation, leaving 172,765 rows, 62,897 represented orders and 23 regions. W2 used the supplied Parquet copy; C2 used CSV. Both hashes are preserved in their saved notebooks. Matching totals do not prove source identity. No raw or curated datasets are submitted. C3 charts use the published rounded C2 aggregate outputs.

Software: Python, pandas, NumPy, Matplotlib, scikit-learn, IPython/Jupyter; historical versions appear in the relevant notebooks. C3 chart code uses the same core libraries and shared palette.

## Key results and limits
K=3 silhouette 0.6235 (K=2: 0.6125); clusters 13/6/4; volume reference ARI 0.361. W3 reports Ward agreement 1.000, not independent validation. Observed temporal break is not proof of migration. No predictive or causal claim.

## Submission and AI
All four notebooks contain saved results. The model was not rerun for C3 because the original CSV is not supplied; C3 chart cells were executed separately from saved summary values. Historical W3 instructions mentioning the dataset are superseded by the C3 no-data requirement. The original C2 contribution record and C3 AI disclosure appear in notebooks 03 and 04. Review before submission; no live AI during defense.
