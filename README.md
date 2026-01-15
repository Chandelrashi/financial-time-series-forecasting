# Financial Time Series Forecasting (ARIMA vs ML vs Hybrid)

## Overview
This repository contains my dissertation project on **financial time series forecasting**, evaluating the performance of:
- Traditional statistical models (ARIMA, Regression)
- Machine learning models (Random Forest, LSTM)
- Hybrid approaches (ARIMA + ML residual modelling)

The work focuses on **accuracy, robustness under volatility, forecast horizon performance, and computational trade-offs** to support decision-making in finance.

## Dissertation Context
- Project: *Financial Time Series Forecasting — Evaluating Performance and Exploring Hybrid Approaches*
- Artefacts included:
  - `dissertation/dissertation.pdf` (full dissertation report)
  - `notebooks/updated_code.ipynb` (implementation notebook)

## Decision Problem
Financial markets are noisy and non-stationary. Traditional models can be interpretable but struggle with regime shifts and nonlinear behaviour, while ML models can improve accuracy but may increase computational cost and reduce interpretability.

This project compares approaches to answer:
- Which model is most reliable under **stable vs volatile markets**?
- How do models behave across **short / medium / long forecast horizons**?
- Can hybrid models balance **accuracy + efficiency**?

## Methods (What I implemented)
### Models evaluated
- **ARIMA** (Box–Jenkins approach)
- **Linear Regression** (with feature diagnostics / multicollinearity checks)
- **Random Forest**
- **LSTM**
- **Ensemble / Hybrid approaches** (including ARIMA-LSTM residual modelling)

### Evaluation metrics
- RMSE, MAE, MAPE (used consistently across model comparisons)

## Results Summary (from dissertation)
Key reported metrics include:

| Model | RMSE | MAE | R² | Notes |
|------|------:|----:|---:|------|
| ARIMA | 4050.34 | 2863.70 | -0.8993 | Interpretable but weak under dynamic conditions |
| Linear Regression | 67.61 | 48.06 | 0.9996 | Strong for linear trends |
| Random Forest | **53.54** | **26.60** | **0.9998** | Best performance among ML models reported |
| LSTM | 906.10 | 625.58 | 0.9055 | Strong sequential learning, higher compute cost |
| Ensemble | 2970.72 | 2453.32 | 0.2921 | Underperformed due to compounded errors |

> Hybrid approaches showed the highest overall accuracy in volatile markets, with **ARIMA-LSTM** reported as the most accurate configuration and achieving up to ~20% RMSE reduction vs standalone approaches in some scenarios. :contentReference[oaicite:1]{index=1}

## Market Conditions & Horizon Insights
- **Stable markets:** traditional models remain competitive and cost-effective  
- **Volatile markets:** ML + hybrid approaches are more adaptable; ARIMA struggles with sudden changes  
- **Short horizon:** LSTM performs strongly due to sequential dependency learning  
- **Long horizon:** hybrid approaches (e.g., ARIMA-RF) can be more stable than pure ML models

These findings align model choice with practical constraints (accuracy vs interpretability vs compute). :contentReference[oaicite:2]{index=2}

## Visual Outputs
Add dissertation screenshots into `assets/` and embed them here:

![Model accuracy comparison](assets/model_accuracy_comparison.png)
![LSTM actual vs predicted](assets/lstm_actual_vs_predicted.png)
![Random Forest actual vs predicted](assets/rf_actual_vs_predicted.png)

## How to Run (Reproducible)
This repo provides the full report and implementation notebook.

Recommended:
1. Open `notebooks/updated_code.ipynb`
2. Install dependencies (create a `requirements.txt` as needed)
3. Run cells sequentially to reproduce preprocessing, training, and evaluation

## Data Note
Datasets referenced in the dissertation were sourced from established platforms (e.g., Bloomberg, Yahoo Finance, Quandl). This repository focuses on **methodology, evaluation, and applied forecasting workflow**. :contentReference[oaicite:3]{index=3}

## Author
Rashi Chandel
