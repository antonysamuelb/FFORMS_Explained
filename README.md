# FFORMS_Explained
Exploration and documentation of my understanding of the FFORMS by Thiyanga S Talagala, Rob J Hyndman & George Athanasopoulos.
* Refer to this link (https://robjhyndman.com/publications/fforms/) for an explanation of the methodology.
* The R package for the same can be found here (https://github.com/thiyangt/seer)
* Other useful repos: https://thiyangt.github.io/fformsviz/fforms.html#yearly

## What is FFORMS?
* FFORMS (Feature-based FORecast Model Selection) selects the best model for a given time series based on features calculated from the time series.
* FFORMS was created to avoid costly time series cross-validation procedures to select the best model.
* It works only for Univariate time series.
## How does FFORMS work?
* First we need to decide what models are to be considered for time series forecasting. Let this be L.
* We need a classification model, to which we can provide inputs of a time series and the classification model can predict which model to use for the best forecasting results.
* Say we have a population of time series data, we sample a few of them.
* We also simulate new time series in order to augment the sample. The original sample and the simulated sample will be called the "reference set".
* Each of the time series in the "reference set" is split into training and test sets.
* For each of the training period set, we calculate specified time series features.
* These time series features serves as input to the classification model.
* We train each time series across all the L models.
* Using each of the L models we forecast over the train data horizon and we evaluate the error
* The labels for the classification model are the models that works best for each time series based on performance over the test data.
## FFORMS has multiple parts
### Augmenting Sample with Simulated Time Series
* This can be done by either generating data from fitted models.
* We can use the gratis package in R too.
### Time Series Features.
#### T
* Length of the time series
#### trend 
* Strength of the trend component in the time series.
#### seasonality_q
* Strength of quarterly seasonality component in the time series.
#### seasonality_m
* Strength of monthly seasonality component in the time series.
#### seasonlity_w
* Strength of weekly seasonality component in the time series.
#### seasonlity_d
* Strength of daily seasonality component in the time series.
#### seasonlity_y
* Strength of yearly seasonality component in the time series.
#### Linearity
* 
#### curvature
#### spikiness
#### e_acf1
#### stability
#### lumpiness
#### entropy
#### hurst
#### nonlinearity
#### alpha
#### beta
#### hwalpha
#### hwbeta
#### hwgamma
#### ur_pp
#### ur_kpss
#### y_acf1
#### diff1y_acf1
#### diff2y_acf1
#### y_acf5
#### diff1y_acf5
#### diff2y_acf5
#### sediff_acf1
#### sediff_seacf1
#### sediff_acf5
#### seas_pacf
#### lmres_acf1
#### y_pacf5
#### diff1y_pacf5
#### diff2y_pacf5
