# Time-Series_Modeling-on-Churn

### RESEARCH QUESTION
How can telecommunications companies predict daily for the next 180 days to manage customer churn better?
### OBJECTIVES
My goals for this analysis are to identify revenue trends and patterns and conduct spectral density analysis. The first goal is to analyze the historical daily revenue data to identify trends, seasonal patterns, and recurring cycles. This helps us understand how revenue has changed over time. The second goal is to analyze the spectral density of the revenue data to identify cyclical patterns in revenue. 

### SUMMARY OF ASSUMPTIONS
Time series models require the data to be stationary to make accurate and meaningful predictions. Non-stationary data can lead to unreliable forecasts. A time series is stationary if its statistical properties, such as mean, variance, and autocorrelation, are constant over time.
Autocorrelation in time series analysis assumes that current values are correlated with past values. Significant autocorrelation indicates that future values depend on previous observations. This is crucial for selecting appropriate model like ARIMA. 

## RESULTS### 
SELECTION OF AN ARIMA MODEL
To identify the most suitable ARIMA model, I used the auto_arima function, which automatically selects the best parameters for the ARIMA model based on the data. This function tests different combinations of p, d, and q parameters and selects the one with the lowest AIC. 
The final and best model is ARIMA(1,1,0)(0,1,0)[90]. The chosen model shown as ARIMA(1,1,0) indicates a first-order autoregressive model (AR=1), first-order differencing (I=1), and no moving average component (MA=0). The Seasonal Component shown as (0,1,0)[90] has no seasonal autoregressive or moving average components but includes seasonal differencing with a period of 90 days.
### THE PREDICTION INTERVAL OF THE FORECAST
The forecast for 180 days includes mean forecast and confidence intervals of 50% Confidence Interval and 95% Confidence Interval. The 50% Confidence Interval is narrower, indicating more likely future values. On the other hand, the 95% Confidence Interval shows a wider range, providing a conservative estimate of future values.  
### A JUSTIFICATION OF THE FORECAST LENGTH
The forecast length of 180 days is based on business relevance, seasonality, and model reliability. Firstly, business relevance specifically focuses on the telecommunications industry. A six-month forecast helps in strategic planning for customer retention efforts and marketing campaigns. Furthermore, given the model’s seasonal component with a 90-day period, the 180-day forecast captures two full seasonal cycles. Lastly, a 180-day forecast makes for a more reliable model. Forecasts beyond this period may introduce higher uncertainty, making them less reliable for practical decision-making.
### MODEL EVALUATION PROCEDURE AND ERROR METRIC
Performance Metric	Score
Mean Absolute Error (MAE)	0.4670
Mean Squared Error (MSE)	0.3246
Root Mean Squared Error (RMSE)	0.5697

The MAE measures the average magnitude of the error in a set of predictions without considering their direction. On average, the model’s predictions are off by about 0.47 million dollars. This indicates how much the forecast deviates from the actual values on a daily basis. 
The MSE measures the average of the squares of the errors. This metric is more sensitive to large errors because squaring the differences magnifies the larger errors more than the smaller ones. An MSE of 0.32 indicates that, on average, the square of the difference between the predicted and actual values is about 0.32. This value is less interpretable on its own because it is squared millions of dollars.
The RMSE is the square root of the MSE and provides error metrics in the same units as the original data, thus making it more interpretable. An RMSE of approximately 0.57 indicates that, on average, the magnitude of the model’s prediction is about 0.57 million errors. 
These performance metrics suggest that while the model has a relatively small average error, there are instances where the error is larger, as indicated by the higher RMSE compared to MAE.
### RECOMMENDATIONS
I have three recommendations for this analysis. 
Firstly, integrate forecasting into business strategy. Use the revenue forecasts to make informed decisions about resource allocation. For example, anticipate periods of lower revenue to plan cost-saving measures. On the other hand, identify periods of expected high churn and proactively implement customer retention strategies with targeted promotion. 
Furthermore, investigate any significant deviation between the forecasted and actual revenue to understand the relying causes. This could involve deeper analysis into specific periods or customer segments. 
Lastly, monitor and update the model regularly. Continuously update the model with new data to improve its accuracy. This will ensure that the model remains relevant and accurate over time. It is also important to retrain the model periodically to capture any shifts in customer behavior. 

