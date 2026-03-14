# Trader Behavior Analysis Based on Market Sentiment

## Project Overview

This project analyzes the relationship between **crypto trader performance** and **market sentiment** using the Fear & Greed Index dataset and historical trader data.
The goal is to understand how trader behavior and profitability change during different sentiment phases such as **Fear, Greed, Extreme Fear, and Extreme Greed**.
By combining sentiment data with trading activity, we explore patterns in trader performance, trade frequency, and risk-taking behavior.

---

## Objectives

The main objectives of this analysis are:

* Understand how **market sentiment affects trader performance**
* Identify patterns in **profitability and trading activity**
* Segment traders based on **frequency and profitability**
* Provide **data-driven trading strategy insights**
* Build a **basic predictive model** to estimate trade success probability

---

## Dataset Description

### 1. Fear & Greed Index Dataset

This dataset represents overall crypto market sentiment on a daily basis.

| Column         | Description                            |
| -------------- | -------------------------------------- |
| timestamp      | Unix timestamp of the sentiment record |
| value          | Numerical sentiment score              |
| classification | Sentiment category (Fear, Greed, etc.) |
| date           | Date of sentiment record               |

---

### 2. Historical Trader Data

This dataset contains trade-level data for multiple traders.

| Column          | Description                       |
| --------------- | --------------------------------- |
| Account         | Trader wallet address             |
| Coin            | Traded asset                      |
| Execution Price | Price at which the trade executed |
| Size Tokens     | Number of tokens traded           |
| Size USD        | Trade value in USD                |
| Side            | Long or Short trade               |
| Timestamp IST   | Trade timestamp                   |
| Closed PnL      | Profit or loss of the trade       |
| Fee             | Trading fee                       |
| Trade ID        | Unique trade identifier           |

---

## Data Preprocessing

The following preprocessing steps were performed:

* Loaded datasets using **Pandas**
* Inspected structure using `shape`, `info()`
* Checked for **missing values**
* Removed **duplicate records**
* Converted timestamps to **datetime format**
* Extracted **Date** from timestamps
* Merged trader dataset with sentiment dataset using the **Date column**

---

## Feature Engineering

Several new features were created to analyze trader behavior:

* **Win Indicator**

  Determines whether a trade was profitable.

* **Daily PnL**

  Calculates total daily profit/loss per trader.

* **Trader Type**

  * Frequent Trader
  * Infrequent Trader

* **Trade Size Segment**

  * Large Trades
  * Small Trades

* **Performance Category**

  * Winner
  * Loser

---

## Exploratory Data Analysis

The following analyses were performed:

### Market Sentiment Distribution

Visualizes how often each sentiment category appears.

### Profit vs Sentiment

Box plots show how trader profitability varies across sentiment conditions.

### Win Rate by Sentiment

Measures how often traders make profitable trades in each sentiment category.

### Trade Frequency by Sentiment

Shows how trader activity changes depending on market sentiment.

### Long vs Short Trades

Examines directional trading behavior.

### Trades Per Day

Shows daily trading activity trends.

### Trader Segmentation

Compares profitability between:

* Frequent vs Infrequent traders
* Winning vs Losing traders
* Large vs Small trades

---

## Machine Learning Model

A simple **Logistic Regression model** was built to predict whether a trade will be profitable.

### Features Used

* Trade Size (USD)
* Encoded Market Sentiment

### Target Variable

* Win (1 if profit, 0 if loss)

### Workflow

1. Train-test split
2. Model training
3. Model evaluation using accuracy

---

## Key Insights

1. **Trading activity increases during Greed and Extreme Greed periods**, suggesting bullish sentiment encourages more market participation.

2. **Profit variability is higher during Extreme Greed**, indicating traders take larger and riskier positions.

3. **Frequent traders exhibit higher volatility in profit and loss**, implying more aggressive trading strategies.

4. **Trade sizes tend to increase during Greed phases**, reflecting increased confidence in market direction.

---

## Strategy Recommendations

Based on the analysis, the following trading insights are suggested:

**1. Risk Reduction During Fear**

During Fear sentiment periods, traders should reduce position size to manage downside risk and avoid overexposure.

**2. Momentum Strategies During Greed**

Momentum-based trading strategies may perform better during Greed periods due to increased trading activity and stronger market trends.

**3. Position Size Management**

Implementing position size limits can help reduce large drawdowns during volatile sentiment shifts.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Project Structure

```
Trader-Sentiment-Analysis
│
├── Data
│   ├── fear_greed_index.csv
│   └── historical_data.csv
│
├── notebooks
│   └── trader_sentiment_analysis.ipynb
│
├── README.md
```

---

## How to Run the Project

1. Clone the repository

```bash
git clone https://github.com/Sharathweb/Trader-Behavior-Analysis
```

2. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Open the notebook

```bash
jupyter notebook
```

4. Run the notebook cells sequentially.

---

## Future Improvements

* Use advanced models such as **Random Forest or XGBoost**
* Incorporate **leverage data and trading volume**
* Perform **time-series sentiment analysis**
* Build a **trading strategy backtesting system**

---

## Author

Sharath Siva Prasad
Data Science Student
