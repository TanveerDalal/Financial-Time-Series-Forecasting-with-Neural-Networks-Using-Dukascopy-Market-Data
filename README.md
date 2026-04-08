# Financial-Time-Series-Forecasting-with-Neural-Networks-Using-Dukascopy-Market-Data
Develop and compare neural network models for short-horizon financial time series forecasting using Dukascopy data, with justified feature engineering, hyperparameter tuning and/or early stopping, and evaluation through multiple error metrics and visualisations.

# 📈 EUR/USD Time Series Forecasting using Neural Networks

## 📌 Project Overview

This project focuses on predicting **next-step returns of the EUR/USD currency pair** using neural network models. The dataset consists of **5-minute interval financial data** obtained from Dukascopy, covering approximately 6 months of market activity.

The goal is to evaluate different neural network architectures and determine whether sequence-based models improve prediction performance over a simple baseline.

---

## 📂 Dataset Description

* **Instrument:** EUR/USD

* **Timeframe:** 5-minute intervals

* **Source:** Dukascopy

* **Features Used:**

  * Open, High, Low, Close
  * Volume
  * Engineered features:

    * Returns
    * Log returns
    * Price range
    * Candle body
    * Moving averages (MA5, MA10)
    * Rolling volatility

* **Target Variable:**

  * Next-step return (regression problem)

---

## ⚙️ Project Pipeline

The project follows a structured pipeline:

1. Data Loading and Cleaning
2. Feature Engineering
3. Train/Validation/Test Split (Time-based)
4. Data Scaling (no leakage)
5. Sequence Creation (20 time steps)
6. Model Training and Evaluation
7. Hyperparameter Optimization

---

## 🧠 Models Implemented

### 1. Dense Neural Network (Baseline)

* Input: Flattened sequences
* Purpose: Provide baseline performance
* Limitation: Does not capture temporal dependencies

---

### 2. LSTM (Long Short-Term Memory)

* Designed for sequential data
* Captures temporal dependencies
* Slight improvement over Dense model

---

### 3. GRU (Gated Recurrent Unit)

* Simpler alternative to LSTM
* Faster training
* Achieved best performance among base models

---

### 4. Tuned GRU (Final Model)

* Hyperparameters optimized:

  * Hidden size
  * Number of layers
  * Learning rate
* Selected based on validation performance

---

## 📊 Results

| Model         | MAE          | RMSE         |
| ------------- | ------------ | ------------ |
| Dense         | ~0.000221    | ~0.000344    |
| LSTM          | ~0.000218    | ~0.000338    |
| GRU           | ~0.000217    | ~0.000337    |
| **Tuned GRU** | **0.000216** | **0.000336** |

---

## 📈 Key Observations

* All models produced predictions close to zero
* Sequence models (LSTM, GRU) provided **only marginal improvements**
* Hyperparameter tuning slightly improved GRU performance
* Models struggled to capture volatility and sharp movements

---

## 🔍 Critical Insights

* Financial returns are **highly noisy and weakly predictable**
* Increasing model complexity does **not guarantee better performance**
* Proper preprocessing and scaling are **crucial for stability**
* Even advanced neural networks have **limited predictive power** in this domain

---

## 🏆 Final Model

The **Tuned GRU model** was selected as the best-performing model based on RMSE.

However, improvements were small, highlighting the inherent difficulty of financial time series prediction.

---

## 🛠️ Technologies Used

* Python
* PyTorch
* NumPy, Pandas
* Matplotlib, Seaborn
* Scikit-learn

---

## 📁 Project Structure

```
notebook.ipynb   # Complete project (single notebook)
README.md        # Project documentation
```

---

## 🚀 How to Run

1. Open the notebook in Google Colab or Kaggle
2. Upload or link the dataset
3. Run all cells sequentially
4. View results, plots, and model comparisons

---

## 📌 Conclusion

This project demonstrates that while neural networks can model financial time series, their effectiveness is limited due to the noisy nature of market data. The results emphasize the importance of realistic expectations and careful evaluation in financial forecasting tasks.

---

## ✍️ Author

Tanveer Dalal

---
