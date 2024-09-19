# S&P 500 Stock Price Prediction

This project focuses on predicting stock prices for companies in the S&P 500 index using both supervised and unsupervised machine learning algorithms. The main goal was to explore different algorithms and evaluate their performance in predicting future stock prices based on historical data.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Algorithms and Models](#algorithms-and-models)
  - [Supervised Learning](#supervised-learning)
  - [Unsupervised Learning](#unsupervised-learning)
- [Results](#results)
- [Model Evaluation](#model-evaluation)
- [Conclusion](#conclusion)
- [Installation and Usage](#installation-and-usage)
- [License](#license)

## Project Overview

In this project, I explored different machine learning techniques to predict the stock prices of companies listed in the S&P 500 index. The focus was to compare both supervised and unsupervised algorithms to determine which method provides better accuracy and performance.

## Dataset

The data for this project was obtained from Kaggle's [S&P 500 stock data](https://www.kaggle.com/datasets/andrewmvd/sp-500-stocks). It includes the historical daily stock prices (Open, High, Low, Close, and Volume) for S&P 500 companies.

- **Dataset Source**: [S&P 500 Stocks Dataset on Kaggle](https://www.kaggle.com/datasets/andrewmvd/sp-500-stocks)
- **Data Features**:
  - Date
  - Open price
  - High price
  - Low price
  - Close price
  - Volume

## Algorithms and Models

### Supervised Learning
For the supervised learning approach, a **XGBoost, Random Forest Regressor and Support Vector Regression (SVR)** models was used to predict the future prices of the stocks.

**Features used**:
- Historical prices (Open, High, Low, Close)
- Volume

### Unsupervised Learning
For unsupervised learning, a **K-Means clustering** algorithm was applied. While clustering is not typically used for prediction, the goal here was to cluster stock data based on similar behavior and trends, which can provide insights into stock groupings and behavior patterns.

**Features used**:
- Historical prices (Open, High, Low, Close)
- Volume

## Results

### Supervised Learning

**To compare model performances, you can view actual price fluctuation below.**

![image](https://github.com/user-attachments/assets/f84b87fe-af02-4eee-b2ab-0ab03d01b0af)

The **XGBoost** model provided the following results:
- **Mean Absolute Error (MAE)**: `66.66`
- **Root Mean Squared Error (RMSE)**: `3.01`
  
![image](https://github.com/user-attachments/assets/c727f677-ea4f-45ba-86be-775b65f52dd8)

The **Random Forest Regressor** model provided the following results:
- **Mean Absolute Error (MAE)**: `15.82`
- **Root Mean Squared Error (RMSE)**: `2.46`

![image](https://github.com/user-attachments/assets/c301b8f3-5731-4639-ba42-f3931f16258a)

The **SVR** model provided the following results:
- **Mean Absolute Error (MAE)**: `686.30`
- **Root Mean Squared Error (RMSE)**: `12.18`

![image](https://github.com/user-attachments/assets/9ad17534-813f-405e-8edf-637b5381253d)

***Overall Evaluation:***
- **XGBoost,** while powerful, might be **having difficulty capturing sudden and extreme price changes or volatility.** There seems to be a significant misalignment in capturing spikes and dips in prices. The predicted prices (red) consistently overshoot or undershoot during large price swings, which can lead to high error metrics.
- **Random Forest Regressor** shows that the predicted prices (red line) follow the actual prices (blue line) closely in most areas, but there are still discrepancies during the spikes. Nevertheless, **best MAE and RMSE scores** are seen in this model.
- **SVR** showed a large deviation between the predicted prices (red) and actual prices (blue). Sharp spikes and volatility are not well captured by the SVR model. It tends to **overestimate and exaggerate the peaks.**

### Unsupervised Learning (K-Means Clustering)

K-Means clustering was used to group stocks based on their historical price trends. The following clusters were identified:
- **Cluster 1 (Dark Blue)**: These could be conservative, blue-chip stocks that exhibit low volatility and steady growth patterns.
- **Cluster 2 (Yellow)**: Stocks in this cluster could be stable but might have occasional fluctuations due to external market factors.
- **Cluster 3 (Orange)**: This cluster could represent mid-level stocks that are not as stable as the first two clusters but don't show as much volatility as more speculative stocks.
- **Cluster 4 (Purple)**: These stocks might be growth or speculative stocks, potentially offering high returns but also with higher risks. They could include technology stocks or companies in emerging markets.
  
![image](https://github.com/user-attachments/assets/10be3ee4-affc-4e38-961c-3b9b76423791)

***Davies-Bouldin Index: 0.775***

**Davies-Bouldin Index (DBI):** This measures to evaluate cluster separation and compactness. Lower values indicate better clustering. A value of 0 means perfect clustering, where clusters are well-separated and compact.
- **DBI < 1:** Generally indicates good clustering. **DBI 0.78** suggests that the clusters are distinct and not overly dispersed.

While this method did not directly predict future prices, it provided useful insights into stock behavior and potential categories that can be further analyzed for future investments.

## Model Evaluation

### Supervised Learning (XGBoost, Random Forest Regressor, SVR)
The Random Forest Regressor model provided more robust stock predictions compared to other models. It performed well on relatively stable stock data but struggled with the inherent volatility and unpredictability of stock markets. The model's simplicity may limit its effectiveness in capturing the complex relationships in stock price movements.

### Unsupervised Learning (K-Means Clustering)
The K-Means clustering method did not provide direct price predictions but allowed for a deeper understanding of stock trends and behaviors. While this method is not meant for time series prediction, it highlighted useful patterns and clusters of stocks that exhibit similar price movements over time.

### Best Fit:
- **Random Forest Regressor** offered more practical predictions for future stock prices but was limited by the volatile nature of the stock market.
- **K-Means** was effective in categorizing stock behavior, which may be useful in a more exploratory phase of stock analysis.

For the purpose of predicting stock prices, **Random Forest Regressor** was the more appropriate model. However, for understanding and grouping stocks by behavior, **K-Means** clustering was valuable.

## Conclusion

This project demonstrates the strengths and weaknesses of both supervised and unsupervised learning approaches in stock price analysis. While Random Forest Regressor provided direct predictions, its performance was limited by the stock market's volatility. On the other hand, K-Means clustering offered insights into stock trends and patterns but did not provide direct price forecasts.

Further work could involve the use of more complex models such as LSTM (Long Short-Term Memory) networks to improve prediction accuracy in supervised learning, as well as other clustering techniques for better stock categorization.

## Installation and Usage

To use the code in this repository:

1. ***Clone the repository:***
   ```bash
   git clone https://github.com/nazifkaraca/SP500-Stock-Prediction.git
   cd SP500-Stock-Prediction

2. ***Install the required libraries:***
   ```bash
   pip install -r requirements.txt

4. ***Run the Jupyter notebook to see the results:***
   ```bash
   jupyter notebook stock_price_prediction.ipynb

## License

This project is licensed under the MIT License.

The dataset used for this project was obtained from [Kaggle's S&P 500 Stocks Dataset](https://www.kaggle.com/datasets/andrewmvd/sp-500-stocks).
