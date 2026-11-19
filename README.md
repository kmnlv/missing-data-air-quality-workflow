# Missing Data Detection and Imputation on Hourly Air Quality Records

> Course: Programming for Descriptive and Predictive Analytics · Unit 02 · Semester 1

## Overview

A complete missing-value workflow on 8,784 hourly air quality records. Three NO2 sensors (`NO2_Location_A/B/C`) contain 120, 580 and 132 missing values respectively. The notebook covers detection, deletion versus imputation, and the effect of each strategy on the distribution of the data. It also discusses MCAR/MAR mechanisms and includes practice prompts based on the NHANES `health_nutrition.csv` dataset.

## Repository structure

- `notebooks/missing-data-air-quality.ipynb` - lecture notebook with executed outputs.
- `data/Airdata.csv` - 8,784 hourly records used for the main workflow.
- `data/health_nutrition.csv` - 14,300 x 50 NHANES-style dataset for the practice exercises.

## Methods

- Detection with `DataFrame.info()`, `isna()`, mean/missing maps, heatmaps and the `missingno` library.
- Deletion with `dropna(axis=..., how=..., thresh=...)`.
- Imputation with mean, median and mode using `fillna`, plus forward-fill and backward-fill for time-ordered records.
- Distribution impact is checked visually before and after each treatment.

## Results

The notebook documents that listwise deletion would discard a large share of rows because missingness overlaps across sensors, while mean/median imputation preserves sample size at the cost of shrinking variance. The temporal ordering of the records motivates forward/backward fill as a plausible alternative for short gaps.

## Requirements

`pandas`, `numpy`, `matplotlib`, `seaborn`, `missingno` and `jupyter`.

## How to run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/missing-data-air-quality.ipynb
```

The original notebook read the CSV from a Google Drive mount. In this repository that path has been changed to the local `data/Airdata.csv`, so it runs from the repository root without Colab.

---
Author: Karla Maria Monroy Alvarez
