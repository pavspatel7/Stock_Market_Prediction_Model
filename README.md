# Stock_Market_Prediction_Model

This project involved developing a machine learning model to predict the direction of the S&P 500 stock index's price movement. The process encompassed several key steps, from data acquisition and preprocessing to model training and evaluation. Here's a detailed overview of the steps taken and the methodologies applied:

### 1. **Data Acquisition**
The historical data for the S&P 500 index was fetched using the `yfinance` library, which provides a convenient interface to Yahoo Finance's financial data. The data retrieved includes daily open, high, low, close prices, and volume information, spanning the maximum available history of the index.

### 2. **Feature Engineering**
To enhance the model's predictive capabilities, additional features were engineered:
- **Relative Strength Index (RSI):** A momentum indicator that measures the magnitude of recent price changes to evaluate overbought or oversold conditions. The RSI was calculated for a 14-day window and added as a new feature to the dataset, providing the model with insight into the index's momentum.

### 3. **Data Preprocessing**
The dataset was prepared for modeling by:
- **Creating a Target Variable:** A binary target variable was defined to indicate whether the index's closing price increased (`1`) or not (`0`) the following day. This transformation turned the problem into a binary classification task.
- **Handling Missing Values and Filtering:** Data starting from January 1, 1990, was considered to focus on more recent and relevant market behaviors. Additionally, any missing values resulting from the RSI calculation or other processes were removed to ensure the model trained on complete records.

### 4. **Dataset Splitting**
The data was divided into training and testing sets, with the last 100 records reserved for testing the model's performance on unseen data. This split allowed for the evaluation of the model's generalization capabilities.

### 5. **Model Training**
A RandomForestClassifier from the `sklearn.ensemble` module was chosen for its robustness and ability to handle non-linear relationships. The model was trained with 100 estimators (trees), using a minimum sample split of 100 to avoid overfitting, and a fixed random state to ensure reproducibility. The features used for training included daily open, high, low, close prices, volume, and the engineered RSI.

### 6. **Model Evaluation**
The model's predictive performance was assessed using the precision metric, which measures the accuracy of the positive predictions (i.e., predicting an increase in the index's price). A precision score signifies the proportion of correct positive predictions out of all positive predictions made.

### 7. **Achieved Outcome**
After training and evaluating the model, a precision score of 61% was achieved. This score indicates that 61% of the model's predictions for the index's price increasing were correct, showcasing the model's ability to effectively identify potential price increases in the S&P 500 index based on the historical data and the calculated RSI feature.

This project illustrates the application of machine learning techniques to financial data, highlighting the potential of quantitative methods in predicting market movements. The inclusion of the RSI as a momentum indicator alongside traditional price and volume information provided the model with a nuanced view of the market, contributing to its ability to forecast price movements with a reasonable degree of accuracy.
