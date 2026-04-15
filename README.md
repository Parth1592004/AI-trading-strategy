# AI-trading-strategy
AI based trading strategy with back testing.
# 📈 AI Trading Strategy using Machine Learning

## 🚀 Project Overview

This project builds and evaluates an **AI-powered trading strategy** using technical indicators and a machine learning model. It compares:

* 📊 A **rule-based trading strategy**
* 🤖 A **machine learning-based strategy (Random Forest)**

The goal is to determine whether ML can outperform traditional technical strategies in predicting stock price movements.

---

## 📂 Dataset

* Source: Yahoo Finance (`yfinance`)
* Stock: **AAPL (Apple Inc.)**
* Time Period: **2020 – 2023**

---

## ⚙️ Features Used

### 1. Moving Averages

* **MA50**: Short-term trend
* **MA200**: Long-term trend
  👉 Used to identify bullish/bearish crossover

### 2. Returns

* Daily percentage change in price

### 3. RSI (Relative Strength Index)

* Measures momentum (0–100 scale)
* Overbought > 70, Oversold < 30

---

## 📊 Strategy 1: Rule-Based Trading

### 📌 Logic

* **BUY (1)** when:

  * MA50 > MA200 (uptrend)
  * RSI < 70 (not overbought)

* **SELL (-1)** when:

  * MA50 < MA200 OR RSI > 70

---

### 📈 Interpretation (Rule-Based Strategy)

* The strategy captures **trend-following behavior**
* Works well during **clear upward/downward trends**
* Avoids buying overbought conditions (RSI filter)

#### ⚠️ Limitations:

* Lagging indicators → late entry/exit
* Performs poorly in sideways markets
* Fixed rules → no adaptability

---

## 🤖 Strategy 2: Machine Learning Model

### 📌 Model Used:

* **Random Forest Classifier**

### 📌 Objective:

Predict:

```
Will the stock go UP tomorrow?
```

### 📌 Target Variable:

* `1` → Price goes up
* `0` → Price goes down

---

### 🧠 ML Workflow

1. Feature Selection:

   * MA50, MA200, RSI

2. Data Split:

   * **80% Training**
   * **20% Testing** (time-based split)

3. Model Training:

   * Random Forest learns patterns between indicators and future returns

4. Predictions:

   * Model predicts buy/sell signals

---

## 📊 Confusion Matrix (Interpretation)

The confusion matrix shows:

|             | Predicted UP        | Predicted DOWN      |
| ----------- | ------------------- | ------------------- |
| Actual UP   | True Positive (TP)  | False Negative (FN) |
| Actual DOWN | False Positive (FP) | True Negative (TN)  |

### 📌 What it tells us:

* **TP** → Correct buy signals
* **TN** → Correct sell signals
* **FP** → Wrong buy (loss risk)
* **FN** → Missed opportunity

👉 A good model has:

* High TP & TN
* Low FP & FN

---

## 📉 Backtesting Strategy

Both strategies are tested using:

* Daily returns
* Signal shifting (to avoid lookahead bias)
* Cumulative returns

---

## 📊 Performance Metrics

### 1. Total Return

* Final profit generated

### 2. Sharpe Ratio

* Risk-adjusted return
* Higher = better performance

### 3. Max Drawdown

* Maximum loss from peak
* Lower = safer strategy

---

## 📈 Results & Interpretation

### 🔹 Rule-Based Strategy

* ✔ Simple and interpretable
* ✔ Works in trending markets
* ❌ Lower adaptability
* ❌ Misses complex patterns

---

### 🔹 ML Strategy

#### 📊 Key Insights:

* Learns **non-linear relationships**
* Adapts better to market changes
* Can outperform rule-based strategy (depending on data)

#### ⚠️ Limitations:

* May **overfit** training data
* Accuracy does not always equal profitability
* Requires proper feature engineering

---

## 📉 Graphs

### 📊 Rule-Based vs Market

![Rule Strategy](performance.png)

### 📊 ML Strategy vs Market

*(Generated in final output plot)*

---

## 🧠 Final Interpretation

* Rule-based strategy is **simple but rigid**
* ML strategy is **adaptive but complex**
* Combining both gives better understanding

👉 Most important takeaway:

> **Prediction accuracy ≠ Trading profitability**

A model must be evaluated using:

* Returns
* Risk (Sharpe ratio)
* Drawdowns

---

## 🚀 Future Improvements

* Add more indicators (MACD, Bollinger Bands)
* Hyperparameter tuning
* Use LSTM / Deep Learning
* Portfolio optimization instead of single stock
* Include transaction costs

---

## 📌 Conclusion

This project demonstrates:

* End-to-end ML pipeline in finance
* Practical backtesting approach
* Real-world evaluation metrics

It serves as a strong foundation for:

* Quantitative finance
* Algorithmic trading
* AI in financial markets

---

## 👨‍💻 Author

**Parth Bhanushali**

---

## ⭐ If you found this useful

Give this repo a star and share your feedback!
