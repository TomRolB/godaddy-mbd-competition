# GoDaddy - Microbusiness Density Forecasting

This repository stores the jupyter notebook which includes all my preprocessing, feature engineering and predictions for [Kaggle's competition](https://www.kaggle.com/competitions/godaddy-microbusiness-density-forecasting) "GoDaddy - Microbusiness Density Forecasting", were I competed against 3,833 teams/individuals.

The goal of the competition was to forecast  microbusiness density (MBD) in each county of the USA for a three-month window. This metric was defined as the number of Microbusinesses per 100 people over the age of 18 in the given county.

## Method

My approach was to construct features based on MBD lags and moving averages. A "lag" is a shifted version of the original values. In other words, each entry of the training and test data has not only the MBD value of the corresponding month, but also those from the previous ones. This introduces a time sense for the model. 

I Included as well the mean and standard deviation for MBD along each USA state. Moreover, I applied linear regression county-wise and used the resulting predictions and slopes as an additional input.

The final predictions were computed with CatBoost over the previously mentioned preprocessing and feature engineering. With this, I reached a SMAPE of 7,95%, i.e. on average, the forecasts were within 7,95% of the actual values.

