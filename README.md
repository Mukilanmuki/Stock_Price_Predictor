# Stock Price Prediction Using LSTM

## Project Overview

This project uses an LSTM (Long Short-Term Memory) neural network to predict stock prices. We applied time-series analysis and various feature engineering techniques to create an effective forecasting model. The project explores historical stock data, processes it for training, and evaluates model performance using various metrics to ensure accurate prediction results.

## Dataset

- **Source**: Historical stock price data from 1988 to 2024.
- **Features**: 
  - Date, Opening Price, High Price, Low Price, Closing Price, Volume.
  - Engineered features such as Lag Features (previous price values) and Rolling Volatility.

## Steps Involved

1. **Data Preprocessing**:
   - Converted the dataset from descending to ascending order.
   - Standardized volume data is achieved by converting values into millions (M) and billions (B).
   - No missing values were present, so no imputation was necessary.

2. **Exploratory Data Analysis (EDA)**:
   - Identified trends in the closing price over time.
   - Detected outliers using a box plot; no action was taken as they represent significant price fluctuations.
   
3. **Feature Engineering**:
   - Lag features were created (previous closing prices over 5, 10 days).
   - Rolling volatility was added to capture stock price volatility.

4. **Modeling**:
   - **LSTM** model was used due to its ability to capture long-term dependencies in time series data.
   - Two LSTM layers (50 units each) were added with dropout to prevent overfitting.
   - Output layer has a single unit for regression (price prediction).

5. **Optimization Attempts**:
   - **Initial Model**: 50 epochs, batch size 32, 5-day time step—gave good results.
   - **Refinement**: Increased time steps to 10 days, resulting in better accuracy.
   - **Final Model**: Best performance achieved with 50 epochs, batch size 32, 10-day time step.
## Results

- **Best Model**: 50 epochs, batch size 32, and 10-day time step sequence.
- The model effectively predicts stock prices with lower error after tuning hyperparameters.

## Evaluation Metrics

- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **Mean Absolute Error (MAE)**

## Future Work

- Explore more advanced features like news sentiment or technical indicators.
- Integrate with external APIs for real-time prediction.


## Usage

### Prerequisites
- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `scikit-learn`, `tensorflow`, `keras`
