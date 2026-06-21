# Customer Segmentation with K-Means Clustering

## Overview
This project segments mall customers into distinct groups based on their age, income, and spending behavior — without using any predefined labels. This is an **unsupervised learning** project, in contrast to the classification and regression projects elsewhere in this portfolio, where the model discovers patterns and groupings in the data on its own.

## Dataset
**Mall Customer Segmentation Data** — a small, clean dataset of mall customers and their spending behavior.

Source: [Kaggle — Customer Segmentation Tutorial in Python](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

| Column | Description |
|---|---|
| CustomerID | Unique identifier for each customer |
| Gender | Male or Female |
| Age | Customer's age |
| Annual Income (k$) | Customer's yearly income, in thousands |
| Spending Score (1-100) | A score assigned based on customer spending behavior |

## Project Workflow
1. **Data Inspection** — Checked dataset structure and confirmed there were no missing values.
2. **Exploratory Data Analysis (EDA)** — Visualized gender distribution, and the distributions of Age, Annual Income, and Spending Score.
3. **Feature Selection & Scaling** — Selected Age, Annual Income, and Spending Score as clustering features, then standardized them using `StandardScaler` (essential for K-Means, which relies on distance calculations).
4. **Finding Optimal K** — Used the **Elbow Method** (plotting WCSS across K=1 to 10) and the **Silhouette Score** to determine the best number of clusters.
5. **Modeling** — Trained a final K-Means model with the optimal number of clusters (K=5).
6. **Cluster Visualization** — Plotted customer segments on an Income vs. Spending Score scatter plot, clearly showing 5 distinct groups.
7. **Cluster Profiling** — Calculated average Age, Income, and Spending Score per cluster to interpret what each segment represents.

## Key Findings
The K-Means model identified 5 distinct customer segments, typically interpretable as:
- **High Income, High Spending** — Premium customers; ideal for loyalty programs and VIP offers.
- **High Income, Low Spending** — Potential customers who aren't spending much; good targets for personalized promotions.
- **Low Income, High Spending** — Budget-conscious but engaged shoppers.
- **Low Income, Low Spending** — Price-sensitive customers, responsive to discounts.
- **Average Income, Average Spending** — The largest, "typical" customer group.

## Tech Stack
- Python
- Pandas, NumPy — data manipulation
- Matplotlib, Seaborn — visualization
- Scikit-learn — `StandardScaler`, `KMeans`, `silhouette_score`

## How to Run
1. Clone this repository.
2. Make sure `Mall_Customers.csv` is in the same folder as the notebook.
3. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn`
4. Open `Customer_Segmentation_KMeans.ipynb` in Jupyter Notebook and run all cells.

## Files
- `Customer_Segmentation_KMeans.ipynb` — full analysis and clustering notebook
- `mall_customers_clustered.csv` — dataset with assigned cluster labels
- `README.md` — project documentation
