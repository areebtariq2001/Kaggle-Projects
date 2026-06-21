# Sales Time Series Forecasting

## Overview
This project analyzes historical retail sales data to uncover trends and seasonal patterns, then forecasts future sales using time series modeling. Unlike the other projects in this portfolio, this one works with **sequential, time-indexed data**, focusing on trend and seasonality rather than independent observations.

## Dataset
**Superstore Sales Dataset** — 4 years of retail transaction records from a global superstore.

Source: [Kaggle — Sales Forecasting (Superstore)](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting)

Key columns used: `Order Date`, `Sales`, `Category`, `Region`.

## Project Workflow
1. **Data Preparation** — Converted `Order Date` to datetime format and aggregated daily transactions into **monthly sales totals**.
2. **Exploratory Data Analysis (EDA)** — Visualized the overall monthly sales trend, and broke down total sales by Category and Region.
3. **Seasonal Decomposition** — Used `statsmodels`' `seasonal_decompose` to separate the sales series into **Trend**, **Seasonality**, and **Residual** components.
4. **Train-Test Split** — Held out the last 6 months as a test set (time-based split, not random, to respect the sequential nature of the data).
5. **Modeling** — Built and compared two forecasting approaches:
   - **Naive Baseline** — repeats the last observed value (a standard benchmark for time series).
   - **Holt-Winters Exponential Smoothing** — captures both trend and seasonality.
6. **Evaluation** — Compared models using MAE and RMSE on the held-out test months.
7. **Future Forecasting** — Used the full historical dataset to forecast sales for the next 6 months.

## Key Findings
- Sales show clear **seasonality**, with a noticeable spike toward the end of the year (Q4 / holiday season).
- The Holt-Winters model outperforms the naive baseline by capturing the underlying trend and repeating seasonal pattern, rather than just assuming sales stay flat.
- This kind of forecast can help a business plan inventory, staffing, and marketing spend ahead of peak demand periods.

## Model Results
| Model | MAE | RMSE |
|---|---|---|
| Naive Baseline | **[XX]** *(replace with your Cell 13 output)* | **[XX]** |
| Holt-Winters | **[XX]** | **[XX]** |

*(Add a short note on how much better Holt-Winters performed compared to the naive baseline — this comparison is the core point of the project, since it shows the value of modeling trend/seasonality explicitly.)*

## Tech Stack
- Python
- Pandas, NumPy — data manipulation and time series resampling
- Matplotlib, Seaborn — visualization
- Statsmodels — seasonal decomposition and Holt-Winters Exponential Smoothing
- Scikit-learn — evaluation metrics (MAE, RMSE)

## How to Run
1. Clone this repository.
2. Make sure `train.csv` is in the same folder as the notebook.
3. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn statsmodels`
4. Open `Sales_Time_Series_Forecasting.ipynb` in Jupyter Notebook and run all cells.

## Files
- `Sales_Time_Series_Forecasting.ipynb` — full analysis and forecasting notebook
- `monthly_sales_aggregated.csv` — cleaned, monthly-aggregated sales data
- `README.md` — project documentation
