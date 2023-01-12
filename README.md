# HourlyEnergyConsumption-Forcast-XGBoost

This is a project to make the XGBoost model to predict the time series data<br/>

* The data source: [Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)

<br/>

The original dataframe look like this: <br/>
![screen-shot](screen-shot.png)<br/>

I reset index to the time series:
```py
df.set_index('Datetime')
```


