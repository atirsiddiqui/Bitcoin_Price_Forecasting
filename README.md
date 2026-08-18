# 📊 BitCoin Price Forecasting — Case Study

## 🎓 Project Overview
This repository presents a case study on **next-day Bitcoin price forecasting** using deep learning models.  
It was developed as part of the **Master in Artificial Intelligence and Applied Data Science** program.  

The project explores **supervised regression in time-series forecasting**, comparing a feedforward **MLP** and a sequence-aware **LSTM** network trained on Bitcoin’s daily OHLCV data (2019–2023).

---

## 📂 Repository Contents
- `data/Bitcoin_Daily.csv` — Raw dataset (daily OHLCV, 2019–2023).  
- `notebooks/BitCoin_Price_Forecasting.ipynb` — Jupyter notebook with full implementation.  
- `reports/Report.md` — Documentation and case study write-up.  
- `results/` — Visualizations (training loss curves, actual vs. predicted plots).  
- `requirements.txt` — Python dependencies for reproducibility.  
- `LICENSE` — Open-source license (MIT recommended).  

---

## 🧠 Problem Definition
- **Task:** Predict Bitcoin’s closing price for day *t+1* using the previous 30 days of closing prices.  
- **Formulation:** Supervised regression / time-series forecasting.  
- **Models:**  
  - **MLP:** Treats the 30-day window as a flat vector.  
  - **LSTM:** Captures sequential dependencies across the 30-day horizon.  

---

## 📊 Key Results
- **Evaluation Metrics:** MSE, MAE, MAPE.  
- **Findings:**  
  - LSTM outperformed MLP with lower error metrics and better tracking of trend reversals.  
  - Both models remain limited by univariate inputs and inability to anticipate exogenous shocks.  

---

## ⚖️ Ethics, Fairness & Responsible AI
- **Not investment advice** — academic case study only.  
- **Bias:** Dataset limited to Bitcoin (2019–2023), biased toward that regime.  
- **Fairness:** Institutional traders have disproportionate access to advanced forecasting tools.  
- **Explainability:** Models are opaque; no feature attribution implemented.  
- **Societal Impact:** Widespread adoption could amplify volatility.  

---

## 🚀 Future Work
- Incorporate multivariate features (OHLCV + sentiment, macro indicators).  
- Explore hybrid architectures (ARIMA + LSTM, Transformers).  
- Add explainability tools (SHAP, LIME).  
- Extend forecasting horizon beyond 1 day.  
- Embed transaction cost modeling for realistic trading evaluation.  

---

## ⚙️ Requirements
Install dependencies with:

```bash
pip install -r requirements.txt
