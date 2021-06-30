---
layout: post
title:      "Modeling Time Series Data"
date:       2021-06-30 16:20:23 +0000
permalink:  modeling_time_series_data
---


## The ARIMA model

The ARIMA model is used to analyze and forecast time series. The acronym stands for Autoregression Integrated Moving Average.

- Autoregression - models the dependent relationship between an observation and lagged observations

- Integrated - refers to differencing raw observations to make the time series stationary.

- Moving Average - the dependency between an observation and a residual error from a moving average model applied to lagged observations

Each of these components has an associated parameter:

- p: the number of lag observations in the model (ie lag order)

- d: the number of times the raw observations are differenced

- q: the size of the moving average window (ie order of moving average)

## Steps to building an ARIMA model

### Data preprocessing

The dates/times should be converted to pandas datetime format, and that column should also be used as the index of the dataframe.

Any resampling needed should be done at this stage. Downsampling will change the time periods from days to months for example. Upsampling will do the reverse. Upsampling will create timestamps with missing data. 

To resolve missing data, it can be forward filled (fill the current missing value with a previous one) or backfilled (filled with the next value). Other defined criteria can be used to fill in missing values (such as using the mean of the column, etc.). Dropping rows with missing data is another option, though care should be taken to not lose important information.

A time series can be assumed to be stationary if it has the following properties over time:
1. The mean of the series is a constant over time.
2. The series shows homoskedasticity, that is the variance is not a function of time.
3. Covariance should also not be a function of time.

Types of trends
1. No trends
2. Linear trend
3. Exponential trend
4. Periodic trend
5. Trend with increasing variance
6. Periodic and upward trend


Testing for trends
1. Rolling statistics
2. Dickey-Fuller test

Method for eliminating trends
1. Log transformations
2. Subtracting the rolling mean
3. differencing

Time series decomposition

The original time series is split into thee component series:
1. Seasonal
2. Trend
3. Random

### Modeling

The ARIMA model should be optimized for the p, d, q parameters discussed above. 

### Forecasting

Once the model is built, it can be used to run a One Step Ahead Forecast against existing data and visualized to see how well the model is forecasting. Then Dynamic Forecast and Future Predictions can also be visualized.



