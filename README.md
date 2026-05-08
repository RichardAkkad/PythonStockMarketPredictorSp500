S&P 500 Stock Market Predictor

About Me

I come from a mathematics and statistics background, which has always been the foundation of how I approach problem solving. More recently, I have been focused on web development and building websites, but I wanted to return to something more analytical and data-driven. This project gave me the opportunity to combine my statistical background with machine learning and Python (which is the language I first started off learning when I learnt programming), which was a great challenge.
Project Overview
This project uses historical S&P 500 index data to predict whether the market will go up or down the following day. It was built entirely in JupyterLab using Python and a range of data science libraries.
The data was downloaded using yfinance, which pulls historical daily price data for the S&P 500 index (ticker: ^GSPC) going back to 1990 — over 9,000 trading days in total.

Libraries Used

yfinance — downloading historical S&P 500 data
pandas — data cleaning and manipulation
scikit-learn — machine learning (Random Forest Classifier)

How It Works

Historical S&P 500 data is downloaded including Open, High, Low, Close and Volume for each trading day
A Target column is created — a value of 1 means the price went up the next day, 0 means it went down
Rolling averages across multiple time horizons (2, 5, 60, 250 and 1000 days) are added as additional predictors
A Random Forest Classifier is trained on this data
Backtesting is used to evaluate the model on unseen data

Results

In the initial model using basic predictors, the precision score was 46% — barely better than random guessing, with the model predicting the market would go up only 13 times out of 250 predictions.
After improving the model by adding rolling average predictors across multiple time horizons, the precision score jumped to 87.5%. The model became far more selective, only predicting an upward move when it had a confidence level above 60%, which significantly improved accuracy.
The historical data also showed that the S&P 500 goes up roughly 48.4% of trading days and down 51.6% of trading days, confirming how difficult it is to beat the market consistently.

Next Steps

Add more predictors such as RSI and moving average crossovers
Test other models such as XGBoost or Logistic Regression
Improve backtesting with more sophisticated evaluation metrics
