# SmartCart — Customer Segmentation System

## Overview
A customer segmentation model that groups customers into distinct behavioral segments based on income, spending patterns, and purchase channel preferences, using unsupervised clustering.

## Dataset
- Source: Kaggle — "SmartCart Customers" dataset
- Features: Demographic data (income, education, marital status, household composition) and behavioral data (spending by product category, purchases by channel, web visits, campaign response)

## Approach
- Preprocessing: Feature scaling with StandardScaler
- Dimensionality reduction: PCA (3 components) for clustering and visualization
- Determining optimal cluster count:
  - Elbow method (WCSS via KneeLocator) → optimal k = 4
  - Cross-validated with silhouette score analysis across k = 2–10
- Final clustering: Agglomerative Clustering (ward linkage, 4 clusters)

## Results
Four distinct customer segments were identified:

| Segment | Income (avg) | Total Spending (avg) | Web Purchases | Catalog Purchases | Store Purchases | Campaign Response Rate |
|---------|-------------|----------------------|----------------|--------------------|--------------------|--------------------------|
| 0       | ~$39.7k     | ~$222                | 3.2            | 1.0                | 4.1                | 7.6%                     |
| 1       | ~$72.8k     | ~$1,237              | 5.7            | 5.5                | 8.7                | 16.7%                    |
| 2       | ~$37.0k     | ~$166                | 2.7            | 0.8                | 3.6                | 14.2%                    |
| 3       | ~$70.7k     | ~$1,190              | 5.8            | 5.0                | 8.4                | 32.0%                    |

Segments broadly separate into **low-income/low-spend** vs **high-income/high-spend** customers, with further distinction by household living situation and campaign responsiveness — segment 3 (high-income, high campaign response) represents the strongest target for marketing campaigns.

## Tech Stack
Python, Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib, kneed

## How to Run
```bash
pip install -r requirements.txt
jupyter notebook smartcart.ipynb
```

## Contributors
Mohammad Uruj Faizan (solo project)
