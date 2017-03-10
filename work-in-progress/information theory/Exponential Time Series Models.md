## Methods
There are several methods we need to pick in order to model any given time series appropriately:

- Simple Exponential Smoothing
    - Finds the level of the time series
- Holt's Linear Trend
    - Finds the level of the time series
    - Additive model for linear trend
- Exponential Trend
    - Finds the level of the time series
    - Multiplicative model for exponential trend
- Holt-Winters Seasonal
    - Finds the level of the time series
    - Additive for trend
    - Multiplicative and Additive for seasonal components

These methods help deal with different scenarios in our time series involving:
    - Linear or exponential trend
    - Constant or increasing seasonality components

For trends that are exponenti al, we would need to use a multiplicative model.

For increasing seasonality components, we would need to use a multiplicative model model as well.

### ETS
Therefore we can generalize all of these models using a naming system for ETS:

#### ETS (Error, Trend, Seasonality)
Error is the error line we saw in the time series decomposition part earlier in the course. If the error is increasing similar to an increasing seasonal components, we would need to consider a multiplicative design for the exponential model.

Therefore, for each component in the ETS system, we can assign None, Multiplicative, or Additive (or N, M, A) for each of the three components in our time series.

#### Examples
A time series model that has a constant error, linear trend, and increasing seasonal components means we would need to use an ETS model of:
    - ETS(N,A,M)
A time series model that has increasing error, exponential trend, and no seasonality means we would need to use an ETS model of:
    - ETS(M,M,N)