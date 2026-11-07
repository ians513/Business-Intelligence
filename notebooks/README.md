# Business Intelligence
## Workshop 2 — DataCo Regional Sales Analysis

### Project Information

**Course:** Business Intelligence  
**Assessment:** W2 — From Exploratory Analysis to Credible Validation  
**University:** Universidad del Desarrollo (UDD)  
**Group:** 67  
**Members:** Ian Spikin Thomas, Juan Pablo Molina  
**Submission Date:** October 23, 2026  
**Repository:** https://github.com/ians513/Business-Intelligence

---

## 1. Project Description

This project continues the analysis developed in Workshop 1 (W1) and Certamen 1 (C1), using the DataCo Supply Chain dataset.

The business problem focuses on differences in recorded commercial activity across regions and product categories. The objective is to identify meaningful patterns in recorded sales behavior while accounting for data quality, temporal coverage, sampling limitations, and potential information leakage.

The principal key performance indicator (KPI) is **recorded units per represented order**, calculated as the total number of recorded product units divided by the number of distinct represented orders.

The unit of observation is an **Order Item**, representing an individual product line within an order. Multiple order items can belong to the same order.

Workshop 2 strengthens the credibility of the previous exploratory analysis through systematic data validation, reproducible sampling, leakage auditing, and an appropriate holdout and validation strategy.

The project remains descriptive and does not claim to demonstrate causal relationships or predictive accuracy.

## 2. Project Structure

The repository is organized as follows:

```text
Business-Intelligence/
│
├── README.md
│
├── legacy/
│   ├── analysis/
│   ├── data/
│   ├── presentation/
│   ├── report/
│   └── README.md
│
└── notebooks/
    ├── README.md
    └── W2_project.ipynb
```

### Directory Descriptions

**legacy/**

Contains the historical project materials from W1 and C1, including previous analyses, datasets, reports, presentations, and documentation. These files are preserved to maintain continuity and traceability.

**notebooks/**

Contains the Workshop 2 Jupyter Notebook and its supporting documentation.

**notebooks/W2_project.ipynb**

Contains the complete W2 analytical workflow, including revised exploratory analysis, data validation, sampling assessment, leakage auditing, holdout design, and management conclusions.

**README.md**

Provides the main documentation of the project, its methodology, data provenance, repository structure, and reproducibility instructions.

## 3. Data Source and Provenance

**Dataset:** DataCo Smart Supply Chain for Big Data Analysis  
**Source:** Mendeley Data  
**Version:** 5  
**DOI:** 10.17632/8gx2fvg2k6.5  
**Source URL:** https://data.mendeley.com/datasets/8gx2fvg2k6/5

The dataset contains historical information about orders, customers, products, categories, geographical regions, discounts, shipping, and transaction statuses.

The original dataset is preserved without modification. Data transformations and exclusions are performed programmatically within the notebook.

The W2 analysis continues using the same data source as W1 and C1, without introducing an unrelated business problem or dataset.

The notebook supports the source CSV file or a compatible Parquet copy.

## 4. Business Objective and KPI

The central business question is:

**How does recorded commercial activity vary across DataCo regions and product categories, and how should these differences be interpreted given the limitations of the observed transactions?**

The principal KPI is calculated as:

**Units per Order = Total Recorded Units / Number of Distinct Represented Orders**

Additional indicators include:

- Total recorded units.
- Number of distinct represented orders.
- Regional and categorical shares.
- Monthly recorded units.
- Order-item quantity distributions.
- Temporal coverage and regional comparability.

These indicators describe the observed dataset rather than total market demand or business profitability.

## 5. Workshop 2 Methodology

### 5.1 W1/C1 Continuity and Feedback

The notebook preserves the original business problem, objective, KPI, and observation unit.

It includes a feedback-to-action assessment based on C1 evidence and justified self-auditing. The analysis documents corrections to previous interpretations and distinguishes verified changes from remaining uncertainties.

### 5.2 Revised Exploratory Data Analysis

The exploratory analysis includes three principal visualizations:

1. Distribution of recorded order-item quantities.
2. Monthly recorded units for selected regions.
3. Regional KPI comparisons using units per represented order.

The analysis considers denominators, missing values, temporal coverage, exclusions, and differences in observation windows.

Conclusions are supported by descriptive evidence, without interpreting statistical associations as causal relationships.

### 5.3 Data Validation

The notebook implements a data dictionary and seven programmatic quality checks addressing relevant dimensions of the dataset.

These checks examine identifier integrity, numerical constraints, status consistency, date logic, within-order consistency, category mappings, and monetary relationships.

Validation outcomes and treatments are documented, including row counts before and after analytical exclusions.

The analytical dataset excludes records with the following order statuses:

- `CANCELED`
- `SUSPECTED_FRAUD`

These exclusions are maintained for continuity with C1 and are explicitly reported.

### 5.4 Sampling and Representativeness

The notebook distinguishes between the target population, the observed dataset, and the final analytical population.

A reproducible subsample of approximately 25% is generated using order-level sampling to preserve the relationship between orders and their corresponding items.

The subsample is compared with the full available analytical dataset using the main KPI and a relevant categorical proportion.

Potential sources of selection and coverage bias are discussed, including limitations in temporal coverage and the representativeness of recorded transactions.

### 5.5 Leakage Audit

The project includes an audit of potential information leakage in a future predictive application.

The audit considers six context-specific risks, such as future information, variables derived from outcomes, repeated entities, and preprocessing performed outside the training subset.

Each risk is evaluated using its status, supporting evidence, potential consequences, and mitigation strategy.

The purpose is to establish defensible analytical practices without introducing an unnecessary predictive model.

### 5.6 Holdout and Internal Validation

The notebook implements a chronological partition of the observed dataset into training, validation, and test subsets.

The splitting procedure considers the business process, observation dates, and the grouping of records belonging to the same order.

The analysis verifies subset sizes, proportions, and inappropriate overlap.

A preprocessing demonstration calculates parameters using training data only and applies the resulting transformation to validation and test data without refitting.

Because the project is descriptive, the holdout is used as an independent robustness assessment rather than a measure of predictive accuracy.

The notebook also acknowledges that previous W1/C1 exploration limits how completely untouched the holdout can be considered.

### 5.7 Management Interpretation

The notebook concludes with a management summary addressing:

- Changes introduced since C1.
- Validated descriptive findings.
- Remaining data and interpretation limitations.
- Implications for commercial analysis.
- Recommended next analytical steps.

The interpretation explicitly separates observed results, analytical assumptions, and managerial recommendations.

## 6. Software and Dependencies

The project was developed using:

- Python 3
- Jupyter Notebook
- pandas
- NumPy
- matplotlib
- IPython
- pathlib
- hashlib

The following command installs the required external libraries:

```bash
pip install pandas numpy matplotlib jupyter pyarrow ipython
```

`pyarrow` is required when the dataset is loaded from a Parquet file. It is not necessary when using only the CSV source.

## 7. How to Run the Workshop 2 Notebook

1. Clone or download the complete GitHub repository.

```bash
git clone https://github.com/ians513/Business-Intelligence.git
```

2. Open the downloaded project in Visual Studio Code or Jupyter Notebook.

3. Verify that the source CSV file or a compatible Parquet file is available.

4. Ensure that the dataset path is included among the candidate paths in the notebook's data-loading section.

5. Install the required Python libraries.

6. Open:

```text
notebooks/W2_project.ipynb
```

7. Select a Python environment with the dependencies installed.

8. Restart the Jupyter kernel.

9. Execute all notebook cells sequentially, from top to bottom.

10. Verify that the validation results, tables, figures, sampling assessment, leakage audit, and data partitions are generated without errors.

11. Save the notebook with all relevant outputs visible.

The notebook uses a fixed random seed of **67** to support reproducibility.

## 8. Reproducibility and Data Integrity

The analytical workflow follows these principles:

- The original dataset is preserved without modification.
- Analytical exclusions are explicitly documented.
- Data quality is assessed through executable checks.
- Row counts and filtering decisions are reported.
- Random sampling uses a fixed seed.
- Related order items are considered in the partitioning strategy.
- Data leakage risks are evaluated before analytical validation.
- Preprocessing parameters are learned from training data only.
- Validation and test information are not used to fit preprocessing parameters.
- Results are interpreted within the limitations of the source data.

The notebook also records dataset characteristics and a SHA-256 file hash for source-data traceability.

## 9. Limitations

The project is based on historical transactions available in the supplied DataCo dataset.

Its findings should not be interpreted as direct evidence of:

- Overall market demand.
- Complete business profitability.
- Causal effects of pricing or discounts.
- Customer behavior outside the observed transactions.
- Representative commercial activity across all regions and periods.
- Future predictive performance.

Differences in time coverage, recording structure, and dataset availability may affect regional comparisons.

The current analysis is descriptive and exploratory.

## 10. Project Continuity

The repository preserves previous W1 and C1 materials in the `legacy/` directory.

Workshop 2 extends the project by strengthening data credibility and establishing a structured validation process.

A possible future analytical direction is forecasting recorded units at a regional, categorical, and monthly level.

Any future predictive implementation should respect chronological ordering, training-only preprocessing, and the leakage prevention principles documented in W2.

No predictive model is required or evaluated as part of the current workshop.

## 11. Individual Contributions

Both group members contributed collaboratively to the project.

**Ian Spikin Thomas:** Participated in the continuity analysis, data preparation, validation methodology, exploratory analysis, interpretation of findings, and final documentation.

**Juan Pablo Molina:** Participated in the project development, methodological review, data analysis, interpretation of results, validation strategy, and preparation of the final deliverables.

Both members are responsible for understanding and defending the submitted analytical decisions.

## 12. AI Use Disclosure

AI tools were used to support coding, organization, writing, documentation, and review of the analytical methodology.

The team remains responsible for verifying the code, reproducing the analytical results, evaluating the interpretations, and explaining the methodological decisions.

AI-generated suggestions were not treated as independent evidence of data quality or analytical validity.

## 13. Submission Information

**Assessment:** Workshop 2  
**Group:** 67  
**Repository:** https://github.com/ians513/Business-Intelligence  
**Notebook:** `notebooks/W2_project.ipynb`

The version submitted for evaluation is identified by its corresponding Git commit or release tag in the submission record.

The repository preserves earlier W1/C1 materials and includes the documentation required to reproduce the W2 analysis.
