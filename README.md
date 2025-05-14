

# 📊 Trader Sentiment Insights

A data science project that analyzes the relationship between **Bitcoin market sentiment** and **trader performance** using real-world data from the **Fear & Greed Index** and **Hyperliquid trading activity**. The goal is to uncover patterns and provide actionable insights to inform smarter crypto trading strategies.

---

## 🚀 Features

* Preprocessing of sentiment and trading datasets
* Merging based on date to align sentiment with trades
* Exploratory Data Analysis (EDA) with visualizations:

  * Sentiment vs. PnL time series
  * Heatmap of PnL by trade side & sentiment
  * Win rate trends for top traders
  * Profitability patterns under various sentiment conditions
* Statistical analysis using correlation and regression
* Strategy insights derived from sentiment-driven trading behaviors

---

## 📁 Project Structure

```
📦 trader-sentiment-insights
├── main.py                 # Main script to run full analysis
├── README.md               # Project overview and documentation

```

---

## 📦 Requirements

Install required libraries via:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

---

## 📊 Input Datasets

1. **Bitcoin Market Sentiment (Fear & Greed Index)**
   Columns: `timestamp`, `value`, `classification`, `date`

2. **Hyperliquid Historical Trader Data**
   Columns: `Account`, `Coin`, `Execution Price`, `Size USD`, `Closed PnL`, `Timestamp IST`, `Side`, `Transaction Hash`, etc.

Ensure the CSV files are downloaded and update their paths in `main.py`:

```python
sentiment_path = r"C:\Users\ACER\Downloads\fear_greed_index.csv"
trader_path = r"C:\Users\ACER\Downloads\historical_data.csv"
```

---

## 🧪 How to Run

Simply run the main script:

```bash
python main.py
```

The script will:

* Load and preprocess both datasets
* Generate multiple visualizations (saved in `/plots`)
* Perform statistical modeling and correlation analysis
* Print actionable trading insights

---

## 📈 Example Visualizations

* `timeseries_sentiment_pnl.png`: Aggregate daily PnL and sentiment index
* `heatmap_pnl_side_sentiment.png`: Average PnL by trade direction vs. sentiment
* `top_traders_win_rate.png`: How top traders perform across sentiment types
* `profitability_vs_sentiment.png`: Profitability distribution across sentiment index

---

## 💡 Key Insights (Sample)

* **Buy during Extreme Fear** conditions often results in higher win rates.
* **Sell during Extreme Greed** may be more profitable but riskier.
* **Monitor 7-day sentiment average** for better trend prediction.

---
