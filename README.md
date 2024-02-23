## LSTM Stock Price Prediction

### Overview

The project utilizes an LSTM model to predict stock prices based on historical data.

The enhanced model now incorporates earnings data alongside other features to improve prediction accuracy. Features include Open, High, Low, Close, Volume, S&P 500 Close, short and long Exponential Moving Averages (EMA), short and long Simple Moving Averages (SMA), Relative Strength Index (RSI), Moving Average Convergence Divergence (MACD), and now, Earnings.

### Results

|                                             AAPL                                              |                                             MSFT                                             |
| :-------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------: |
| ![AAPL](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/predictions/AAPL.png) | ![TSM](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/predictions/MSFT.png) |
|                                             TSLA                                              |                                             TSM                                              |
| ![TSLA](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/predictions/TSLA.png) | ![MSFT](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/predictions/TSM.png) |

|                                             Training Loss                                              |
| :----------------------------------------------------------------------------------------------------: |
| ![Training Loss](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/predictions/loss.png) |

### Data Preprocessing

The dataset was obtained from Yahoo Finance using the yfinance library and then processed to include the following steps:

1. Dropping 'Dividends' and 'Stock Splits' columns.
2. Adding technical indicators:

- S&P 500 Close
- EMA Short
- EMA Long
- SMA Short
- SMA Long
- RSI
- MACD
- EPS Estimate
- Reported EPS
- Surprise(%)

3. Scaling the features using MinMaxScaler for optimal LSTM performance.

### Model Architecture

The LSTM model consists of:

- Bidirectional LSTM layers to capture patterns from both past and future data points
- Dense layers with L1_L2 regularization to mitigate overfitting
- Dropout layers to improve generalization
- An EarlyStopping callback is employed to halt training when the validation loss ceases to decrease, preventing overfitting.

### Evaluation Metrics

The model's performance was evaluated using the following metrics:

- R-squared (R²): 0.87 on average, indicating a high level of predictive accuracy
- Mean Absolute Percentage Error (MAPE): 2.0% on average, suggesting low prediction errors

![Model](https://github.com/Jason-Wuuuu/stock_price_prediction/blob/main/predictions/score.png)
