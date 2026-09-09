# SmartCart Segmentation System

A customer segmentation project that groups retail customers into distinct segments based on their demographics, spending behavior, and purchase channel preferences — using unsupervised machine learning.

## What it does

The notebook takes a raw customer dataset and:

1. **Cleans the data** — fills missing income values, removes outliers (extreme ages and incomes).
2. **Engineers new features** — customer age, total tenure (days since joining), total spending across product categories, and total number of children.
3. **Simplifies categories** — consolidates education levels (e.g. Basic/2n Cycle → Undergraduate) and marital status into a simpler "living situation" feature (Alone / Partner).
4. **Encodes and scales** — one-hot encodes categorical features and standardizes all numeric features.
5. **Reduces dimensionality** — applies PCA to project the data into 3 components for clustering and visualization.
6. **Finds the optimal number of clusters** — using the elbow method (WCSS) and silhouette scores.
7. **Segments customers** — clusters using both K-Means and Agglomerative (Ward linkage) clustering, and compares results.
8. **Profiles each segment** — summarizes income, spending, purchase channels, and demographics per cluster to make each segment actionable.

## Tech stack

- **Python**
- **pandas** — data cleaning and manipulation
- **matplotlib / seaborn** — visualization (pairplots, heatmaps, cluster plots)
- **scikit-learn** — preprocessing (OneHotEncoder, StandardScaler), PCA, KMeans, AgglomerativeClustering, silhouette scoring
- **kneed** — automatic elbow-point detection for choosing the optimal number of clusters

## Dataset

Uses a customer marketing dataset (`smartcart_customers.csv`) with fields such as income, education, marital status, number of children, purchase recency, spending by product category, and number of purchases per channel (web, catalog, store).

> Note: the dataset is not included in this repository — see `.gitignore`.

## How to run

1. Clone this repository.
2. Place `smartcart_customers.csv` in the project root.
3. Install dependencies:
   ```
   pip install pandas matplotlib seaborn scikit-learn kneed
   ```
4. Open and run `smartcart.ipynb` in Jupyter.

## Output

The final output is a set of customer segments (clusters), each profiled by average income, spending, tenure, purchase channel usage, and household composition — useful for targeted marketing or personalization strategies.
