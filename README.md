# BTC Trend Direction Prediction Using Machine Learning

This project develops a machine-learning–based trend-following model for Bitcoin (BTC-USD) using 
daily OHLCV data and engineered technical indicators. The goal is to classify whether Bitcoin is 
in an **uptrend** or **downtrend**, defined using the moving-average crossover rule:

**Signal = 1 if MA10 ≥ MA60 else 0**,  
**Signal = 0 otherwise**.

Two models are trained:
- **Logistic Regression** (baseline)
- **XGBoost Classifier** (primary model)

Both models are evaluated using standard performance metrics and are backtested against a 
Buy-and-Hold strategy.

---

## 📁 Repository Structure

project/
├── notebooks/
│ └── btc_trend_model.ipynb # Main notebook
│ ├── data/
│   ├── raw_btc.csv # Downloaded Yahoo Finance data (daily)
│   ├── btc_indicators.csv # Indicators after preprocessing
│   └── btc_features_labeled.csv # Final ML dataset
│ ├── artifacts/
│   ├── xgb_model.pkl
│   ├── logreg_model.pkl
│   ├── scaler.pkl
│   └── selected_features.pkl
├── README.md
└── requirements.txt



## 🚀 Project Workflow

1. **Data Download & Cleaning**  
   - Daily OHLCV Bitcoin data from Yahoo Finance  
   - Cleanup of columns, removal of NaNs  
   - No MultiIndex headers  

2. **Feature Engineering**  
   - Momentum indicators (RSI, ROC, MACD, Stochastics)  
   - Trend indicators (EMAs, Bollinger Bands)  
   - Volatility indicators (ATR, CCI)  
   - Volume indicators (OBV, CMF, ADL)  
   - PCA and XGBoost feature importance analysis  

3. **Modeling**  
   - Logistic Regression  
   - XGBoost  
   - Chi-Square feature selection  

4. **Evaluation**  
   - Accuracy, precision, recall, F1  
   - ROC-AUC  
   - Confusion matrix  
   - Backtest vs Buy & Hold  

5. **Results Summary**  
   - Models achieve ~92% accuracy and ~0.98 ROC-AUC  
   - ML strategy is conservative and reduces downside risk  
   - Buy & Hold outperforms during major bull runs  
   - ML strategy outperforms in sideways/down periods  



