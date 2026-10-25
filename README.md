# Retail Sales EDA and Visualization

Exploratory Data Analysis (EDA) of retail sales data using Python, pandas, Matplotlib and Seaborn. The project examines data quality, distributions, relationships, trends and outliers to find what drives revenue and profit, and to prepare the data for later modelling.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![pandas](https://img.shields.io/badge/pandas-EDA-150458)
![Seaborn](https://img.shields.io/badge/Seaborn-visualization-4c72b0)
![License](https://img.shields.io/badge/License-MIT-green)

## Table of Contents

- [Project Overview](#project-overview)
- [Key Questions](#key-questions)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [How to Run](#how-to-run)
- [Methodology](#methodology)
- [Visualizations](#visualizations)
- [Expected Insights](#expected-insights)
- [Timeline](#timeline)
- [Tools Used](#tools-used)
- [Future Work](#future-work)
- [License](#license)

## Project Overview

EDA is the stage where we learn what the data contains before building models. This project follows a structured, time-boxed plan (about 32 hours) that moves from data understanding and cleaning to statistical summaries, visual exploration and written insights.

**Business goal:** understand which products, regions and customers drive revenue and profit, and where margin is being lost (for example through heavy discounting).

## Key Questions

1. Is the data complete, consistent and trustworthy?
2. How are sales, profit, quantity and discount distributed?
3. How do sales and profit change over time? Is there seasonality?
4. Which categories, regions and segments perform best and worst?
5. Does discounting increase sales, or only reduce profit?
6. Which variables are related to profit?
7. Are outliers errors or genuine high-value events?
8. Do customer groups behave differently?

## Dataset

- **Source:** public retail dataset (for example Superstore sales or Online Retail transactions). Replace with your own data in `data/raw/`.
- **Typical columns:** order ID, order date, ship date, customer ID, segment, region, category, sub-category, sales, quantity, discount, profit.
- Raw data is never modified; cleaned data is saved to `data/processed/`.

> If the dataset is too large for GitHub, add its download link here instead of committing the file.

## Project Structure

```
eda-retail-sales/
|-- data/
|   |-- raw/                  # untouched source files
|   `-- processed/            # cleaned dataset
|-- notebooks/
|   |-- 01_data_understanding.ipynb
|   |-- 02_cleaning_quality.ipynb
|   |-- 03_univariate_analysis.ipynb
|   |-- 04_bivariate_multivariate.ipynb
|   |-- 05_time_series.ipynb
|   `-- 06_outliers_insights.ipynb
|-- src/
|   |-- load.py               # data loading and date parsing
|   |-- clean.py              # missing values, duplicates, validation
|   |-- summarize.py          # numeric and categorical summaries
|   |-- plots.py              # reusable plotting functions and style
|   `-- outliers.py           # IQR and z-score outlier flags
|-- reports/
|   `-- figures/              # exported charts (PNG, 300 dpi)
|-- requirements.txt
|-- README.md
`-- LICENSE
```

## Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/eda-retail-sales.git
cd eda-retail-sales

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

**requirements.txt**

```
pandas
numpy
scipy
matplotlib
seaborn
jupyter
plotly        # optional, for interactive charts
ipywidgets    # optional
```

## How to Run

1. Place the dataset in `data/raw/`.
2. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
3. Run the notebooks in order from `01` to `06`.
4. Exported figures are saved in `reports/figures/`.

## Methodology

| Stage | What is done |
|---|---|
| 1. Data understanding | Shape, data types, cardinality, sample rows |
| 2. Quality and cleaning | Missing values, duplicates, validity rules (e.g. ship date after order date), consistent text |
| 3. Univariate analysis | Mean, median, standard deviation, quantiles, skewness, kurtosis, normality tests, frequency tables |
| 4. Bivariate and multivariate | Pearson and Spearman correlation, group comparisons, ANOVA or Kruskal-Wallis, chi-square tests |
| 5. Time series | Resampling, rolling averages, seasonality heatmaps, year-over-year comparison |
| 6. Outliers and synthesis | IQR and z-score flags, manual review, written insights |

## Visualizations

| Question | Plot | Library |
|---|---|---|
| Distribution of a numeric variable | Histogram with KDE | Seaborn |
| Spread and outliers | Box and violin plots | Seaborn |
| Totals per category | Sorted bar chart | Seaborn |
| Two numeric variables | Scatter with regression line | Seaborn |
| Many numeric variables | Correlation heatmap, pair plot | Seaborn |
| Trend over time | Line plot with rolling mean | Matplotlib / Seaborn |
| Seasonality | Year-by-month heatmap | Seaborn |
| Ranking and Pareto | Bar plus cumulative line | Matplotlib |
| Missing data | Missingness heatmap | Seaborn |

**Design principles:** colorblind-friendly palettes, diverging colors centered on zero for profit and correlation, bar charts starting at zero, titles that state the finding, labelled axes with units, and consistent colors for the same category across figures.

## Expected Insights

- Sales and profit are right-skewed; a small share of customers produces most revenue (Pareto pattern).
- Sales peak in the final quarter with a repeating yearly pattern.
- Profit falls and turns negative above a certain discount level.
- Some high-revenue sub-categories have thin or negative margins.
- Regional profit differences are largely explained by product mix and discounting.

These are hypotheses to test, not assumptions. Actual findings are documented in the notebooks and in `reports/`.

## Timeline

| Phase | Hours |
|---|---|
| Planning and setup | 3 |
| Data understanding | 2 |
| Quality and cleaning | 4 |
| Univariate analysis | 4 |
| Bivariate and multivariate analysis | 5 |
| Time-series exploration | 3 |
| Outlier analysis | 2 |
| Visual polish and optional interactivity | 3 |
| Synthesis and reporting | 3 |
| Review and buffer | 3 |
| **Total** | **32** |

## Tools Used

- **Python 3.10+**
- **pandas, NumPy, SciPy** for data handling and statistics
- **Matplotlib and Seaborn** for static visualizations
- **Plotly and ipywidgets** (optional) for interactivity
- **Jupyter Notebook** for analysis and documentation

## Future Work

- Interactive dashboard (Streamlit or Dash)
- Sales forecasting using the seasonality findings
- Customer segmentation (RFM and clustering)
- Pricing and discount optimization experiments

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

**Your Name**
GitHub: [@your-username](https://github.com/your-username)
