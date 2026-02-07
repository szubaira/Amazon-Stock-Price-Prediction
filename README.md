## **Time-Series Forecasting of Amazon (AMZN) Stock Prices Using the Facebook Prophet Algorithm**

### **Project Overview**

The objective of this project was to predict the stock price of Amazon (AMZN) 30 days into the future to support short-term investment decision-making. Using a historical dataset from Yahoo Finance, I implemented a Facebook Prophet forecasting model to identify underlying trends and seasonal patterns. The model successfully projected a 30-day price trajectory, which was subsequently validated against real-market data from Google Finance to assess predictive accuracy.

### **Business Understanding**

Stakeholders in this analysis include retail investors and portfolio managers who require reliable automated tools to navigate the high volatility of the technology sector. The core business problem involves the difficulty of predicting stock fluctuations influenced by complex seasonality and market noise. By leveraging an additive regression model like Prophet, this project provides a scalable method for stakeholders to quantify potential price movement, thereby reducing reliance on purely qualitative market analysis.

### **Data Understanding**

The analysis utilized a historical stock price dataset (AMZN.csv) sourced from Yahoo Finance.

* **Timeframe**: The data spans from October 27, 2021, to October 26, 2022.
* **Key Features**: The dataset includes daily Open, High, Low, Close, and Adjusted Close prices, along with trading Volume.
* **Exploration & Cleaning**: Initial exploratory data analysis (EDA) involved visualizing the closing price trends using Plotly to identify historical peaks and troughs. The data was preprocessed to meet Prophet’s requirements, specifically renaming columns to 'ds' (datestamp) and 'y' (target value).
* **Limitations**: Stock prices are influenced by exogenous factors such as interest rate hikes, earnings reports, and geopolitical events which are not inherently captured by a univariate time-series model relying solely on historical price data.

### **Modeling and Evaluation**

This project implemented the **Facebook Prophet** model, a robust forecasting tool designed for handling seasonality and missing data in time-series.

* **Model Implementation**: The model was trained on the previous year's daily closing prices and configured to predict a 30-day "out-of-sample" period.
* **Evaluation Metrics**: The model's performance was evaluated by comparing the forecasted values (yhat) against actual November 2022 market prices from Google Finance. Key visual metrics included:
* **Trend Components**: Decomposition of the stock’s overall growth trend versus weekly and yearly seasonality.
* **Uncertainty Intervals**: The model provided upper and lower bounds (yhat_upper and yhat_lower) to quantify the confidence level of the 30-day forecast.

### **Conclusion**

The analysis demonstrates that the Facebook Prophet model is an effective baseline for capturing the cyclical nature of Amazon's stock price. Based on the results, the model identifies specific day-of-the-week effects and general trend directions that can inform entry and exit points for short-term traders.

**Future Steps:**

* **Hyperparameter Tuning**: Optimize the "changepoint_prior_scale" to better adjust for sudden shifts in market volatility.
* **Multivariate Analysis**: Integrate additional regressors such as trading volume or macroeconomic indicators (e.g., inflation rates) to improve prediction accuracy during periods of market instability.
* **Sentiment Analysis Integration**: Incorporate Natural Language Processing (NLP) of financial news headlines as a complementary feature to account for non-numerical market drivers.
