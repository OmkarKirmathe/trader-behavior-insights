Trader Behavior Insights Using Market Sentiment

Overview

This project explores the relationship between market sentiment and trader performance using historical trade data and the Bitcoin Fear–Greed Index.
The objective is to identify how different sentiment regimes influence profitability, win rates, and risk-taking behavior, and to derive insights that can inform smarter trading strategies.

Datasets:

1. Historical Trader Data

Trade-level data containing execution details, position size, direction, fees, and realized PnL.

~211,000 individual trades.

2. Bitcoin Market Sentiment Data

Daily Fear–Greed Index values with sentiment classification.

~2,600 daily observations.

Project Workflow

1. Data Understanding (01_data_understanding.ipynb)

Inspected dataset structure, columns, and data types.

Verified time granularity differences between trade data (intraday) and sentiment data (daily).

Assessed data quality and feasibility of joining datasets using date alignment.

2. Data Cleaning & Merge (02_data_cleaning_merge.ipynb)

Converted Unix timestamps (milliseconds) into human-readable datetime format.

Extracted trade dates for alignment with daily sentiment.

Merged trade data with sentiment data using date-based joining.

Validated merge correctness and identified dates without available sentiment data.

Created the final processed dataset:

output/master_trader_sentiment.csv

3. Sentiment vs Performance Analysis (03_analysis_sentiment_vs_performance.ipynb)

Analyzed trader behavior across sentiment regimes using:

Average PnL per trade

Win rate (profitable vs losing trades)

Risk proxy using position size (USD)

Comparisons were performed across:

Fear

Greed

Extreme Greed

Neutral sentiment

4. Insights & Interpretation (04_insights_summary.ipynb)

Consolidated analytical findings into clear, business-oriented insights.

Highlighted non-obvious behavioral patterns linking sentiment, risk-taking, and performance.

Derived practical implications for sentiment-aware trading decisions.

Key Findings

Greed periods show the highest average profitability, despite not having the highest win rate.

Extreme Greed exhibits the highest win rate but lower average PnL, indicating frequent small wins offset by larger losses.

Risk-taking (position size) is highest during Extreme Greed and Fear, but this does not translate to better returns.

Neutral market conditions consistently show the weakest performance across all metrics.

Project Structure

trader-behavior-insights/
│
├── data/
│   ├── raw/
│   │   ├── historical_data.csv
│   │   └── fear_greed_index.csv
│   └── processed/
│       └── master_trader_sentiment.csv
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_cleaning_merge.ipynb
│   ├── 03_analysis_sentiment_vs_performance.ipynb
│   └── 04_insights_summary.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore

Tools Used

Python

Pandas

NumPy

Matplotlib

Jupyter Notebook

How to Run

Install dependencies:

pip install -r requirements.txt


Run notebooks sequentially from:

01_data_understanding.ipynb

to 04_insights_summary.ipynb

Author

Omkar Dnyaneshwar Kirmathe