# IBM and Facebook Stock Prediction using LSTM
This project leverages an LSTM model to predict stock prices for IBM and Facebook by analyzing historical data. 
The focus is on capturing sequential dependencies in time-series data for improved forecasting accuracy. Key steps include data preprocessing, model building, and evaluation of predictive performance

## Access the Project
[IBM and Facebook Stock Prediction using LSTM](https://colab.research.google.com/drive/12f44JQHXEqdZugxM_URas3coyr70HwxR?usp=sharing)

## International Business Machines Corporation (IBM) and Facebook Stock Data
- IBM Dataset: Contains approximately 14,663 rows of daily stock data.
- Facebook Dataset: Similar in structure to IBM, with around 1,980 rows of daily stock data as well.
- Columns:
  - Date: Indicates the trading date for each entry.
  - Open: Opening price of the stock on a given day.
  - High: The highest trading price for the stock on that day.
  - Low: The lowest trading price.
  - Close: The closing price, which is the main target for prediction.
  - Volume: Number of shares traded during that day.

## Data Preprocessing
### Import Libraries and Datasets
- Load necessary libraries and datasets for both IBM and Facebook stocks.
### Data Cleansing
- Missing Values Check: Ensure no missing values.
- Duplicate Check: Confirm no duplicate rows.
### Data Distribution
Visualize data distribution using density plots to understand the spread of each feature.
### Outlier Detection
Use box plots to examine outliers; most outliers were found in the 'Volume' column.
### Date Conversion
Convert the "Date" column to datetime format and set it as the index for easier handling of time series data.

## Data Splitting for Model Input and Output
- Convert stock prices and timestamps into arrays to facilitate LSTM processing.
- Define window size and horizon:
  - Window Size: Number of past time steps used for each prediction.
  - Horizon: Number of future steps to predict.
  - Split data into training (80%), validation (10%), and testing (10%) sets.

## LSTM Model Architecture
- Baseline LSTM Model :
  - LSTM Layer: Contains 50 units to learn temporal dependencies.
  - Dense Output Layer: Predicts the closing price based on learned patterns.
  - Model Summary:
    - Layer | Type | Output Shape | Param #
    - LSTM (units=50): Captures sequential patterns with 10,400 parameters.
    - Dense (units=1): 1 neuron predicting the next closing price.
   
## Model Training and Evaluation
1. Training Configuration
  - Compile the model with Mean Squared Error (MSE) as the loss function.
  - Train with a batch size of 64 for 15 epochs to ensure convergence.
2. Loss Analysis
  - Track Mean Absolute Error (MAE) and Mean Squared Error (MSE) over epochs to monitor performance.
3. Evaluation Metrics
  - Evaluate using RMSE, MAE, and MAPE for IBM and Facebook datasets.
  - Visualize predictions against real values to assess tracking effectiveness.

## Comparison with Modified LSTM Model
The modified LSTM model with dropout regularization and fewer LSTM units demonstrates a slight improvement, reducing overfitting and achieving lower error metrics than the baseline.
