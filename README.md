## LSTM Stock Price Prediction
This repository contains a Jupyter notebook demonstrating the use of a Long Short-Term Memory (LSTM) network for predicting stock prices. The model uses historical stock price data, technical indicators, and the S&P 500 index as inputs to forecast future stock prices.

### Overview
The project utilizes an LSTM model to predict stock prices based on historical data. The model is trained using a variety of features, including Open, High, Low, Close, Volume, S&P 500 Close, short and long Exponential Moving Averages (EMA), short and long Simple Moving Averages (SMA), Relative Strength Index (RSI), and Moving Average Convergence Divergence (MACD).

### Results
Loss             |  Prediction
:-------------------------:|:-------------------------:
![Model](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/output/loss.png) | ![Model](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/output/prediction.png)


### Data Preprocessing
The dataset was obtained from Yahoo Finance using the yfinance library and then processed to include the following steps:

Dropping 'Dividends' and 'Stock Splits' columns
Adding technical indicators: S&P 500 Close, EMA Short, EMA Long, SMA Short, SMA Long, RSI, MACD
Scaling the features using MinMaxScaler for optimal LSTM performance

### Model Architecture
The LSTM model consists of:
- Bidirectional LSTM layers to capture patterns from both past and future data points
- Dense layers with regularization to prevent overfitting
- Dropout layers to improve generalization
- An EarlyStopping callback is employed to halt training when the validation loss ceases to decrease, preventing overfitting.

### Evaluation Metrics
The model's performance was evaluated using the following metrics:
- R-squared (R²): 0.86, indicating a high level of predictive accuracy
- Mean Absolute Percentage Error (MAPE): 2.72%, suggesting low prediction errors


![Model](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/output/score.png)
