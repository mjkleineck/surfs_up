# Surfs Up Analysis

## Overview
The purpose of this analysis is to determine whether or not the climate in Hawaii is condusive for running a surf shop that also sells ice cream.

## Results
![June Temperatures](https://github.com/mjkleineck/surfs_up/blob/main/June_Temps.png) ![December Temperatures](https://github.com/mjkleineck/surfs_up/blob/main/December_Temps.png)

* June's average temperature is nearly four whole degrees warmer than December. It's unlikely that small of a difference in temperature would deter folks from surfing or eating ice cream in December.
* June's 25th percentile and 75th percentile are both within one standard deviation of the mean. The temperature in June remains reasonably constant.
* December's 25th percentile and 75th percentile are both within one standard deviation of the mean. The temperature in December remains reasonably constant.

## Summary
Based on the temperature data for June and December, it's reasonable to conclude that there is not a large fluctuation in temperature. The climate is quite temperate and condusive for surfing and eating ice cream year-round. With so much data available from various weather stations for temperature and precipatation year round, it would be recommended to run queries for temperature data in the months between June and December, i.e. April and September, or even widen the queries to examine December and January, and June and July. It would also be recommended to examine the rainfall in those time frames too. Below are a few additional queries to consider running.

April Temperatures
```
april_temps = session.query(Measurement.date, Measurement.tobs).\
    filter(func.strftime("%m", Measurement.date) == "04").all()
```

September Temperatures
```
sept_temps = session.query(Measurement.date, Measurement.tobs).\
    filter(func.strftime("%m", Measurement.date) == "09").all()
```

June Precipitation
```
june_precip = session.query(Measurement.date, Measurement.prcp).\
    filter(func.strftime("%m", Measurement.date) == "06").all()
```

December Precipitation
```
dec_precip = session.query(Measurement.date, Measurement.prcp).\
    filter(func.strftime("%m", Measurement.date) == "12").all()
```
