# Prophet Analysis & Forecasting
To forecast our profit, profit margin, sales, and returned $ amount, we turned to Facebook Prophet - an open source code to forecast time series data. This code works best with data that has strong seasonality and several seasons of data. Based on our initial exploration, we felt that our data was a good fit for this code.

## Results
On a one-year term, we found that the confidence interval fora data forecasted up to one year out was unfortunately too large for confident, accurate prediction. This did, however, illustrate strong negative seasonality for sales on Mondays, as well as in March and May.
![prophet_sales](https://user-images.githubusercontent.com/90879979/157747081-39a93198-1655-466f-8ec7-e0fb0aa7b98c.png)
