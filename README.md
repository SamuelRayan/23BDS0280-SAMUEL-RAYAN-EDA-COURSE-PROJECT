# Exploratory Data Analysis – Telco Customer Churn

**Course Project · Exploratory Data Analysis Lab**
**Samuel Rayan · 23BDS0280**

An end-to-end exploratory data analysis of the **Telco Customer Churn** dataset in Python. It covers data import and cleaning, univariate, bivariate and multivariate analysis, time series forecasting, clustering and principal component analysis.

## Repository contents

| File | Description |
|---|---|
| [`23BDS0280-SAMUEL RAYAN(EDA COURSE PROJECT).ipynb`](23BDS0280-SAMUEL%20RAYAN%28EDA%20COURSE%20PROJECT%29.ipynb) | Jupyter notebook with all code and outputs |
| [`23BDS0280-SAMUEL RAYAN(EDA COURSE PROJECT).pdf`](23BDS0280-SAMUEL%20RAYAN%28EDA%20COURSE%20PROJECT%29.pdf) | Full project report (PDF export of the notebook) |

## Dataset

- **Source:** [telco customer churn.csv](https://raw.githubusercontent.com/salemprakash/EDA/main/Data/telco%20customer%20churn.csv)
- **Size:** 7,043 customers × 21 variables
- **Variables:** customer demographics (`gender`, `SeniorCitizen`, `Partner`, `Dependents`), account details (`tenure`, `Contract`, `PaperlessBilling`, `PaymentMethod`), subscribed services (phone, internet, security, backup, streaming, etc.), billing (`MonthlyCharges`, `TotalCharges`), and the target variable `Churn`.
- **Data quality:** 36 missing values across 9 columns (34 rows affected), handled with median and mode imputation.

## Project structure

The notebook is split into sections, one for each lab module:

| Section | Topic | What's covered |
|---|---|---|
| **PDF 2** | Data import, transform & basic statistics | Head/tail, structure, summary statistics, missing-value detection, row removal, mean/median/mode/forward/constant imputation, duplicates, factor conversion, renaming, range, variance, SD, IQR |
| **PDF 3** | Data cleaning & univariate analysis | Dropping sparse columns, imputation, duplicate & data-type checks, case conversion, IQR outlier detection and removal, histograms (with density curve), violin and dot plots, proportions, bar and pie charts |
| **PDF 4** | Bivariate analysis | Contingency tables, stacked and grouped bar plots, heatmap, violin plots, titles/labels/legends |
| **PDF 5** | Multivariate analysis | Scatter plots encoding 3 and 4 variables (colour + shape), parallel coordinate plot |
| **PDF 6** | Time series analysis | Monthly series of average `MonthlyCharges` by tenure month, trend plot, seasonal decomposition, ACF/PACF, ARIMA(1,1,1) fit and 12-month forecast with confidence intervals |
| **PDF 7** | 1D, 2D & ND analysis | Frequency & relative frequency, row/column percentages, grouped mean/median/SD, correlation matrix heatmap |
| **PDF 8** | Clustering | **K-Means:** scaling, k = 2, WCSS for k = 1–10, elbow plot, final model. **Hierarchical:** Euclidean distance, Ward's method, dendrogram, cut into 3 clusters |
| **PDF 9** | Principal component analysis | PCA summary & loadings, scree plot, biplot, PCA scores, PC1 vs PC2 scatter |

## Key findings

- **Churn rate:** about **26.5%** of customers churned (1,868 of 7,040 labelled records).
- **Tenure** is bimodal. Peaks at very new customers (< 6 months) and long-term customers (~72 months).
- **Time series:** average monthly charges rise with tenure. The ARIMA(1,1,1) forecast levels off at about **76.3**.
- **K-Means:** the elbow method picks **k = 4** customer segments (sizes 1,957 / 1,746 / 1,142 / 2,174). One segment is made up of senior citizens, and the others split by tenure and spend.
- **Hierarchical clustering** (Ward's method, 3 clusters) gives groups of 4,722 / 1,155 / 1,142.
- **PCA:** PC1 explains **54.6%** of the variance and PC1 + PC2 together explain **81.3%**. PC1 is driven by `TotalCharges`, `tenure` and `MonthlyCharges`, and PC2 mostly by `SeniorCitizen`.

## Tech stack

Python · pandas · NumPy · Matplotlib · Seaborn · SciPy · scikit-learn · statsmodels

## How to run

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn statsmodels jupyter
jupyter notebook "23BDS0280-SAMUEL RAYAN(EDA COURSE PROJECT).ipynb"
```

The dataset is loaded straight from its URL, so you don't need to download anything else.
