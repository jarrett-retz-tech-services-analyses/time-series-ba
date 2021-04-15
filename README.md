# time-series-ba

Exploration of the impacts of COVID deaths on Boeing (BA) daily price. To view the full report in the browser, view the `report.md` file.

Below is the **Abstraction**

## Abstraction

In a prior analysis, using an ordinary least squares regression, I created a model that explained 55.7% of the variation in Boeing (BA) common stock pricing using a 7-day rolling average for U.S COVID-19 mortalities. Additionally, I found this statistic had a correlation with the daily price of **-0.749**. 

Recently, I learned about time-series analysis and I wanted to revist this data with new tools. 

I split the data into a train and test set, then I used an ARIMA (Auto Regressive Integrated Moving Average) model to and predict prices for the test set.

I created multiple models, one using the SPY (SPDR S&P ETF Trust) security as a benchmark to see if the 7-day rolling mortality statistic outperformed the SPY as a predictor or helped to improve the predictions.

I created the three models, used the models to predict the price for 25 days, took the difference in the predictions from the test data set, sqaured the differences, and added them for each model. The results were:

- Using just the **SPY index**, the sum of the difference between predicted and actual prices squared was **39.64275095954604**
- Using just the **COVID data**, the sum of the difference between predicted and actual prices squared was **80.52527950668268**
- Using **both the SPY and the COVID data**, the sum of the difference between predicted and actual prices squared was **16.425098154198338**
