Bitcoin Sentiment and Trader Performance Analysis
This project analyzes the relationship between Bitcoin market sentiment (using the Fear & Greed Index) and trader performance (using historical trade data from Hyperliquid). It uncovers patterns in trading behavior, quantifies sentiment's impact on profitability, and provides actionable trading strategies.
Features

Data Preprocessing: Aligns timestamps, cleans data, and engineers features like profitability and win rate.
Exploratory Data Analysis (EDA): Visualizes sentiment vs. trader performance through six intuitive plots.
Statistical Analysis: Computes correlations and regression models to quantify sentiment's effect on PnL.
Actionable Insights: Recommends strategies like buying during extreme fear and reducing trade size in greed.

Datasets
The analysis uses two datasets (not included in this repository due to privacy):

Bitcoin Market Sentiment Dataset (fear_greed_index.csv):
Columns: timestamp, value (0–100), classification (e.g., "Extreme Fear"), date (DD-MM-YYYY).
Source: Typically from providers like alternative.me.


Historical Trader Data (historical_data.csv):
Columns: Account, Coin, Execution Price, Size Tokens, Size USD, Side, Timestamp IST (or Timestamp), Start Position, Direction, Closed PnL, Transaction Hash, Order ID, Crossed, Fee, Trade ID.
Source: Hyperliquid trading platform.
Note: Assumes Bitcoin trades (Coin == 'BTC').



Assumption: Datasets must have overlapping date ranges for merging. Place them in a data/ directory or update file paths in the script.
Prerequisites

Python: Version 3.8 or higher.
Dependencies:pip install pandas numpy matplotlib seaborn scikit-learn



Installation

Clone the repository:git clone https://github.com/your-username/bitcoin-sentiment-trader-analysis.git
cd bitcoin-sentiment-trader-analysis


Install dependencies:pip install -r requirements.txt

Or manually:pip install pandas numpy matplotlib seaborn scikit-learn


Place datasets (fear_greed_index.csv, historical_data.csv) in the data/ directory or update paths in analyze_sentiment_trader_performance.py.

Usage

Ensure datasets are accessible (e.g., in data/).
Run the script:python analyze_sentiment_trader_performance.py


Outputs:
Console:
Data summaries (columns, samples).
Merged data shape and sample.
Correlation and regression results.
Profitability metrics for extreme fear/greed.
Trading strategy recommendations (e.g., "Buy during Extreme Fear").


Interactive Plots (close each to view the next):
Time-series: Sentiment vs. aggregate PnL.
Heatmap: PnL by trade side and sentiment.
Top traders’ win rates by sentiment.
Profitability vs. sentiment scatter.
Win rate by sentiment bar.
Trade size by sentiment box.


Saved Plots: PNG files in plots/ directory (e.g., timeseries_sentiment_pnl.png).



Directory Structure
bitcoin-sentiment-trader-analysis/
├── data/
│   ├── fear_greed_index.csv        # Sentiment dataset (user-provided)
│   └── historical_data.csv         # Trader dataset (user-provided)
├── plots/                          # Output directory for plots
├── analyze_sentiment_trader_performance.py  # Main script
├── requirements.txt                # Dependencies
└── README.md                       # This file

Troubleshooting

Plots Not Displaying:
Ensure Matplotlib backend supports interactive display:import matplotlib
matplotlib.use('TkAgg')  # Add before import matplotlib.pyplot

Test:import matplotlib.pyplot as plt
plt.plot([1, 2, 3], [4, 5, 6])
plt.show()


In Jupyter, use %matplotlib inline or %matplotlib tk.


Empty Merged Data:
Check date ranges:print("Sentiment Date Range:", sentiment_df['date'].min(), sentiment_df['date'].max())
print("Trader Date Range:", trader_df['date'].min(), trader_df['date'].max())


Ensure datasets overlap in time.


No Bitcoin Trades:
Verify Coin values:print(trader_df['Coin'].unique())


Remove filter in script if no BTC trades:# trader_df = trader_df[trader_df['Coin'] == 'BTC']




Timestamp Parsing Errors:
Inspect trader timestamps:print(trader_df['Timestamp IST'].head())  # or trader_df['Timestamp']


Update pd.to_datetime format if needed (e.g., format='%Y-%m-%d %H:%M:%S').


Permission Errors:
Ensure write access to plots/ directory.
Change output path:output_dir = r"path/to/writable/directory"





Example Insights
Based on typical crypto trading patterns:

Buy in Extreme Fear: Higher win rates when Fear & Greed Index < 25.
Sell in Extreme Greed: Capitalize on overbought markets when Index > 75.
Risk Management: Reduce trade size during greed to mitigate volatility.
Top Traders: Emulate traders with high win rates in fear (see top_traders_win_rate.png).


