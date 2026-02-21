# COVID-19 Data Analysis: Maryland County-Level Case Clustering

Exploratory data analysis of Maryland COVID-19 case data across 24 counties, using K-means clustering to classify counties by outbreak severity.

## Overview

This project analyzes COVID-19 case counts reported by Maryland's Department of Health, broken down by county and facility type (nursing homes, state/local facilities, correctional institutions). The raw dataset uses a wide format with one column per county; the analysis reshapes this into a long format suitable for aggregation and clustering.

K-means clustering (k=3) groups the 24 counties into low, medium, and high incident tiers based on total case counts. The analysis reveals that Baltimore County, Baltimore City, and Montgomery County form the high-incident cluster, while most rural counties fall into the low-incident tier.

## Key Techniques

- Data reshaping with `pandas.melt` (wide → long format, 732 rows → 17,568 observations)
- Missing value imputation and datetime parsing
- K-means clustering with StandardScaler normalization
- County-level aggregation and cluster labeling

## Project Structure

```
d797-ai-ml-foundations/
├── notebooks/
│   └── covid_analysis.ipynb    — Full analysis notebook with outputs
└── data/
    └── cleaned_covid_data.csv  — Cleaned long-format dataset (17,568 rows)
```

## Results

| Cluster         | Counties                                        | Avg Cases |
|-----------------|-------------------------------------------------|-----------|
| High Incident   | Baltimore, Baltimore City, Montgomery            | ~280,000  |
| Medium Incident | Anne Arundel, Prince George's, Washington        | ~114,000  |
| Low Incident    | 18 remaining counties (Allegany through Somerset) | <65,000   |

The clustering confirms that Maryland's COVID-19 burden was heavily concentrated in the Baltimore metro area and Montgomery County (DC suburbs), consistent with population density patterns.

## How to Run

### Prerequisites
```bash
pip install pandas numpy scikit-learn
```

### Run the Analysis
```bash
jupyter notebook notebooks/covid_analysis.ipynb
```

The notebook loads, cleans, reshapes, clusters, and exports the data. The cleaned output is saved to `data/cleaned_covid_data.csv`.

## Dataset

**Maryland COVID-19 Dataset** — 732 records across 24 counties and 5 facility types, spanning April 2020 through early 2021. Source: Maryland Department of Health open data portal.

## Author

Anthony Perry — M.S. Computer Science, Western Governors University
