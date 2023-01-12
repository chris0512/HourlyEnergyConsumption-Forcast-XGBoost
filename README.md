# HourlyEnergyConsumption-Forcast-XGBoost

This is a project to make the XGBoost model to predict the time series data<br/>

* The data source: [Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)

<br/>

The original dataframe look like this: <br/>
![screen-shot](screen-shot.png)<br/>

I reset index to the time series:
```py
# Set time series as index
df = df.set_index('Datetime')
df.index = pd.to_datetime(df.index) # cast index from object to index
df
```
![datetime](date-time.png)

