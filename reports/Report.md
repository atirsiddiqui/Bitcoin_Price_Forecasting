# 📊 Bitcoin Price Forecasting — Project Report

## 🎓 Course Context
This project was developed as part of the **Master in Artificial Intelligence and Data Science** program.  
Objective: To critically interpret, communicate, and document Machine Learning and Deep Learning outcomes in a responsible and ethical manner, applied to a globally relevant problem — **cryptocurrency price forecasting**.

---

## 🧩 Part 1 — Problem Definition & Business Understanding
- **Task:** Predict Bitcoin’s closing price for day *t+1* using the previous 30 days of closing prices.  
- **Formulation:** Supervised regression / time-series forecasting.  
- **Models:**  
  - **MLP:** Treats the 30-day window as a flat vector.  
  - **LSTM:** Captures sequential dependencies across the 30-day horizon.  

**Business Relevance:**  
- Traders & Market Makers → optimize entry/exit timing.  
- Exchanges & Risk Desks → calibrate margin requirements.  
- Portfolio Managers → rebalance allocations based on forecasted momentum.  

---

## 🔍 Part 2 — Exploratory Data Analysis
- Dataset: **Bitcoin Daily OHLCV (2019–2023)**.  
- Observations:  
  - Non-stationary behavior with bull/bear cycles.  
  - Volatility clustering: large moves followed by more large moves.  
  - SMA crossovers (7-day vs 30-day) highlight trend reversals.  

---

## ⚙️ Part 3 — Data Preprocessing
- Normalization: MinMaxScaler applied to closing prices.  
- Windowing: 30-day lookback → next-day target.  
- Chronological split: 80% train / 20% test (no shuffling).  
- Input formats:  
  - **MLP:** `(samples, 30)`  
  - **LSTM:** `(samples, 30, 1)`  

---

## 🏗️ Part 4 — Model Implementation
- **MLP:** 3-layer feedforward network (ReLU activations).  
- **LSTM:** Sequence model with hidden state propagation.  
- Shared training setup: Adam optimizer, MSE loss, 10 epochs, LR=0.001.  

---

## 📊 Part 5 — Model Evaluation
- **Metrics:** MSE, MAE, MAPE (in real USD).  
- **Results:**  
  - MLP → MSE: 2.07M | MAE: 1,267.47 | MAPE: 5.66%  
  - LSTM → MSE: 1.05M | MAE: 732.33 | MAPE: 3.14% 
- **Finding:** LSTM tracks trend reversals more closely, confirming the sequence-aware hypothesis.  

---

## 💡 Part 6 — Business Interpretation
- **Volatility Challenge:** Models cannot anticipate exogenous shocks (regulation, macro news, whale trades).  
- **Comparative Insight:** LSTM shows modest improvement over MLP, but both remain autoregressive trackers.  
- **Business Value:**  
  - Risk reduction via position sizing.  
  - Enhanced trade timing with SMA crossover signals.  
  - Faster reaction to reversals with LSTM.  
- **Limitations:**  
  - Univariate input only.  
  - Non-stationary regimes reduce generalization.  
  - No transaction cost modeling.  
  - Forecast horizon limited to 1 day.  

---

## 🤖 Ethics, Fairness & Responsible AI
- **Not Investment Advice:** Academic case study only.  
- **Bias:** Dataset limited to Bitcoin (2019–2023).  
- **Fairness:** Institutional traders have disproportionate access to advanced tools.  
- **Explainability:** Models are opaque; no feature attribution implemented.  
- **Societal Impact:** Widespread adoption could amplify volatility.  
- **Responsible Use:** Requires disclaimers, human oversight, monitoring, and risk limits.  

---

## ✅ Conclusion
- LSTM outperforms MLP in short-horizon Bitcoin forecasting, especially at trend reversals.  
- Both models are constrained by univariate features and inability to anticipate shocks.  
- Deep learning forecasts should **support, not replace** informed human judgment in financial decision-making.  

---

## 🚀 Future Work
- Incorporate multivariate OHLCV + sentiment/macro data.  
- Explore hybrid models (ARIMA + LSTM, Transformers).  
- Add explainability tools (SHAP, LIME).  
- Extend forecasting horizon beyond 1 day.  
- Embed transaction cost modeling for realistic evaluation.  
- Adaptive training for regime shifts.  

---
📌 *This report documents the methodology, results, ethical reflections, and future directions of applying deep learning to volatile financial time-series forecasting.*
