# Business Intelligence  
# C1 - DataCo Regional Sales Analysis

## Project Information

**Course:** Business Intelligence  
**Assessment:** C1 - From the W1 Project to Defensible Evidence  
**Group:** 67  
**Members:** Ian Spikin Thomas, Juan Pablo Molina  
**Submission Date:** September 29, 2026  

## Project Description

This project develops the commercial line selected in W1 using the DataCo Supply Chain dataset.

The analysis focuses on differences in recorded sales behavior across regions and product categories. The objective is to identify relevant patterns using measures such as recorded units, represented orders, category shares, and units per order, while considering the limitations of the available data.

The project also reviews data quality, temporal coverage, exclusions, and comparability before interpreting the exploratory results.

## Project Structure

The project is organized as follows:

```text
GROUP_67_C1/
│
├── README.md
│
├── report/
│   └── GROUP_67_C1_Report.pdf
│
├── analysis/
│   └── GROUP_67_C1_DataCo_Regional_Sales_Analysis.ipynb
│
├── data/
│   └── DataCoSupplyChainDataset.csv
│
└── presentation/
    └── GROUP_67_C1_Slides.pdf
```

## Files

### report/GROUP_67_C1_Report.pdf

Contains the complete analytical report, including:

- selected problem and evolution from W1,
- documentary support,
- seven-step problem definition,
- data preparation and quality assessment,
- Five Cs,
- exploratory data analysis,
- interpretation and limitations,
- future machine learning and dashboard feasibility,
- process record,
- individual contributions,
- AI use and verification,
- individual reflections,
- references.

### analysis/GROUP_67_C1_DataCo_Regional_Sales_Analysis.ipynb

Jupyter Notebook containing the complete reproducible analysis.

The notebook includes:

- W1 alternatives and selected problem,
- seven-step problem definition,
- measurement definitions,
- data loading and profiling,
- observation unit and temporal coverage,
- Five Cs assessment,
- exploratory commercial analysis,
- normalized comparisons by order,
- discount analysis,
- conclusions and limitations,
- future ML and dashboard feasibility,
- process record and reproducibility checks.

All relevant outputs, tables, figures, and interpretations are saved in the notebook.

### data/DataCoSupplyChainDataset.csv

Dataset used for the analysis.

It contains information related to:

- orders,
- order items,
- customers,
- products,
- categories,
- regions,
- discounts,
- sales,
- shipping,
- delivery performance.

**Source:**  
DataCo Smart Supply Chain for Big Data Analysis  
Mendeley Data  
https://data.mendeley.com/datasets/8gx2fvg2k6/5

## Data Source

**Dataset:** DataCo Smart Supply Chain for Big Data Analysis  
**Source:** Mendeley Data  
**Published:** March 12, 2019  
**Version:** 5  
**DOI:** 10.17632/8gx2fvg2k6.5  

The dataset included in the submission is the source used to reproduce the reported analysis.

## Unit of Observation

One row represents an **Order Item**, meaning a product line recorded within an order.

Therefore:

- one row does not represent one customer,
- one row does not necessarily represent one complete order,
- one order may contain several order items.

This distinction is important when calculating and interpreting commercial indicators.

## How to Run the Analysis

1. Download or extract the complete `GROUP_67_C1` folder.
2. Open:

```text
analysis/GROUP_67_C1_DataCo_Regional_Sales_Analysis.ipynb
```

3. Verify that the dataset is available in:

```text
data/DataCoSupplyChainDataset.csv
```

4. Restart the Jupyter kernel.
5. Run all notebook cells from top to bottom.
6. Confirm that all tables, figures, and reproducibility checks are generated without errors.
7. Save the notebook with all outputs visible.

## Software and Libraries

The analysis was developed using:

- Python 3
- Jupyter Notebook
- pandas
- NumPy
- matplotlib
- pathlib
- IPython

Required libraries can be installed using:

```bash
pip install pandas numpy matplotlib jupyter
```

## Data Preparation

The original dataset is kept unchanged.

The analysis creates a commercial subset by excluding records with the following order statuses:

- `CANCELED`
- `SUSPECTED_FRAUD`

These exclusions are explicitly documented and validated in the notebook.

The notebook also checks:

- dataset dimensions,
- required columns,
- duplicate rows,
- duplicate identifiers,
- missing values,
- date coverage,
- unique orders,
- unique customers,
- order-status distribution,
- number of retained and excluded records.

## Reproducibility

The notebook must be executed from top to bottom in the documented order.

Project-relative paths are used so that the analysis can be reproduced after extracting the project folder on another computer.

The submitted notebook includes saved outputs corresponding to the submitted code and dataset.

The reproducibility section records:

- dataset source,
- number of rows and columns,
- identifier checks,
- missing-value checks,
- temporal coverage,
- filtering decisions,
- retained commercial population,
- analytical decisions and validations.

## Main Analysis Scope

The commercial analysis includes:

- recorded units by region,
- distinct represented orders,
- units per order,
- category shares by region,
- discount-band comparisons,
- temporal coverage checks,
- sensitivity to excluded order statuses.

The analysis is descriptive and exploratory.

The results should not be interpreted as evidence of:

- causal effects of discounts,
- total market demand,
- profitability,
- complete regional performance,
- customer demand outside the observed transactions.

## Future Project Continuity

The selected commercial line can continue toward:

### Machine Learning

A possible future task is forecasting next-month recorded units by region and category.

Possible unit of analysis:

```text
Region × Category × Month
```

Possible inputs include:

- historical recorded units,
- represented orders,
- lagged values,
- category shares,
- calendar information.

### Dashboard

A future dashboard could support commercial analysts or category managers using indicators such as:

- recorded units,
- represented orders,
- units per order,
- category share.

Possible filters include:

- month,
- region,
- category,
- customer segment,
- order status.

## Individual Contributions

Both members worked collaboratively throughout the project and contributed at a similar level.

**Ian Spikin Thomas:**  
Contributed to the problem definition, data preparation, exploratory analysis, interpretation of results, and final deliverables.

**Juan Pablo Molina:**  
Participated in the project framing, data review, analytical development, discussion of findings, and preparation of the final materials.

## AI Use

AI tools were used to support writing, code review, organization of the analysis, and communication of results.

All consequential analytical suggestions were reviewed against the dataset, notebook outputs, and project requirements before being accepted.

The final interpretation and responsibility for the submitted analysis remain with the team.

## Final Reproducibility Checklist

Before submission, verify that:

- the notebook runs from top to bottom,
- all outputs are saved,
- the dataset path works after extraction,
- the report PDF is included,
- the presentation PDF is included,
- the notebook is included,
- the required data are included,
- the README matches the final project structure,
- no credentials, temporary files, or virtual environments are included.
