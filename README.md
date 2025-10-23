
# Trader Behavior Insights — Bitcoin Sentiment vs Hyperliquid Trader Performance
## 🔗 Google Colab Links
- [Notebook 1 – Main Analysis](https://colab.research.google.com/drive/1fBqnO1WaJN5yMP6HFe0zwR8GOzAftwUu?usp=sharing)

**Objective:** Explore the relationship between market sentiment (Fear/Greed Index) and trader performance (closed PnL, win rate, leverage usage) using the provided datasets from Hyperliquid.

**Files:**

*   `historical_data.csv`: Contains detailed trade data.
*   `fear_greed_index.csv`: Contains historical Fear and Greed Index data.

**Analysis Performed:**

1.  **Data Loading and Preparation:**
    *   Loaded trade and sentiment data into pandas DataFrames.
    *   Cleaned column names.
    *   Converted timestamp columns to datetime objects and extracted trade dates.
    *   Calculated additional metrics such as `is_profit`, `abs_pnl`, and `pnl_pct`.
    *   Filter data to include only trades with closed PnL.
2.  **Daily Metrics Aggregation:**
    *   Aggregated trade data to daily metrics (total PnL, trade count, win rate, volume, mean absolute PnL, average leverage).
    *   Merged daily metrics with sentiment data.
3.  **Sentiment Analysis:**
    *   Visualized daily total PnL with sentiment markers over time.
    *   Analyzed the distribution of daily total PnL by sentiment using boxplots.
    *   Calculated and visualized the average daily win rate by sentiment.
    *   Performed statistical tests (Mann-Whitney U, t-test) to compare PnL distributions between Fear and Greed periods.
    *   Calculated lagged correlations between sentiment and daily total PnL.
4.  **Top/Bottom Account Analysis:**
    *   Identified top and bottom performing accounts based on total PnL.
    *   Calculated and compared daily metrics (mean total PnL, win rate, trade count, average leverage) for top and bottom account cohorts across different sentiment classifications.
5.  **Predictive Modeling:**
    *   Built a RandomForestClassifier model to predict trade profitability (`is_profit`).
    *   Included features such as trade size, leverage, notional, and lagged sentiment.
    *   Evaluated the model using AUC and classification report.
    *   Analyzed feature importances using SHAP values to understand feature contributions to the model's predictions.

**Key Findings:**

*   [Summarize findings from the Conclusion section of the notebook, e.g., lack of statistically significant difference in PnL/win rate between Fear and Greed, weak lagged correlations, differences in performance between top/bottom accounts across sentiments, importance of `side_buy` in the predictive model.]

**Recommendations & Next Steps:**

*   [Include recommendations and suggested next steps from the Conclusion section of the notebook, e.g., reducing leverage during Fear periods, flagging accounts with increased leverage during Greed, using short lagged sentiment in risk models, running backtests, adding volatility as a feature, exploring Granger causality.]

**Instructions:**

1.  Run the cells in the provided notebook sequentially.
2.  Ensure the necessary libraries are installed (`gdown`, `shap`, `lightgbm`, `statsmodels`).
3.  The notebook will download the required datasets, perform the analysis, generate plots in the `/content/outputs` directory, and save processed data and results in the `/content/csv_files` directory.
