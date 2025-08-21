<h1>Forecasting U.S. New Plant & Equipment Expenditures (1964–1976)</h1>

<h2>Description</h2>
This was a final project for a time series analysis course where I applied multiple <b>time series techniques</b> to model and forecast <b>U.S. new plant and equipment expenditures</b> from 1964 to 1976. The dataset, sourced from the <b>tsdl</b> package in R, contains 52 quarterly observations.

The goal was to explore whether the expenditure patterns could be effectively modeled using transformations and seasonal ARIMA models, and to generate forecasts of future spending behavior.

The report includes <b>Box-Cox transformations</b>, differencing to remove <b>trend and seasonality</b>, model identification through ACF/PACF plots, model selection via <b>AICc</b>, and diagnostic testing to ensure residuals were white noise.
<br />


<h2>Languages and Utilities Used</h2>

- <b>R (R Markdown for reporting & visualization)</b>
- <b>RStudio</b>
- <b>Git & GitHub for version control</b>
- <b><b>tsdl</b>, <b>forecast</b>, <b>MASS</b>, and <b>MuMIn</b> (R packages)

<h2>Dataset</h2>

- <b>Source:</b> [Quarterly U.S. New Plant/Equipment Expenditures (1964-1976)](https://github.com/FinYang/tsdl)
- <b>Size:</b> 52 quarterly observations (1964-1976)
- <b>Target Variable:</b> U.S. plant & equipment expenditures in billions (numeric, time series)

<h2>Methods</h2>

- <b>Exploratory Data Analysis</b>
  - Identified upward trend, quarterly seasonality, and increasing variance
- <b>Transformations</b>
  - Box-Cox transformation (λ = 0.5) to stabilize variance
  - Differencing (lag 1) to remove trend
  - Seasonal differencing (lag 4) to remove seasonality
- <b>Model Identification</b>
  - ACF/PACF plots to suggest potential SARIMA models
- <b>Model Fitting</b>
  - Compared multiple SARIMA models using <b>AICc</b>
- <b>Diagnostics</b>
  - Residual analysis: Shapiro-Wilk, Box-Pierce, Ljung-Box, and McLeod-Li tests
  - Confirmed residuals followed white noise
 
<h2>Results</h2>

- <b>Best Model:</b> SARIMA(0,1,0)(0,1,1)<sub>4</sub>
- <b>AICc:</b> -106.71 (lowest among candidates)
- <b>Diagnostics:</b> Passed all normality and independence tests
- <b>Forecast Performance:</b> Forecasts closely matched actual values in the testing set (last 10 quarters), with true values falling inside confidence intervals

These results demonstrate that <b>time series forecasting techniques (Box-Cox + SARIMA) can effectively model seasonal economic expenditure data</b>.

<h2>Results Visualization</h2>

- <b>Diagnostic Plots</b>
  - Histogram and Q-Q plots of residuals confirmed approximate normality
  - ACF/PACF plots of residuals showed no significant autocorrelations
  - Residual time series showed no trend or seasonality 
- <b>Forecasting Plots:</b>
  - Forecasted values (with 95% confidence intervals) tracked closely with actual expenditures
  - Zoomed-in view of the test set (last 10 quarters) demonstrated strong predictive accuracy
  - True expenditure values consistently fell within forecast confidence bands

These results illustrate that the <b>SARIMA(0,1,0)(0,1,1)<sub>4</sub> model captured both trend and seasonality effectively</b>, making it a strong candidate for forecasting economic time series data.

<h2>Project Structure</h2>

- <b>`ForecastUSExpend.pdf`</b> → Full project report, including methods, results, visualizations, and discussion (pdf)
- <b>`forecasting_code.Rmd`</b> → R Markdown file with all analysis steps (data transformation, modeling, diagnostics, forecasting)
- <b>`ForecastUSExpend.html`</b> → Full project report, including methods, results, visualizations, and discussion (pdf)
 
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
