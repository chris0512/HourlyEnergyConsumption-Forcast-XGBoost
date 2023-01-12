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
![datetime](date-time.png) <br/>

Plot the df
```py
import seaborn as sns
color_pal = sns.color_palette()
df.plot(style='.',
        figsize=(15, 5),
        color=color_pal[0],
        title='PJME Energy Use in MW ')
```
![screenshot](screen-shot2.png)

Train Test Split
```py
#train test split
train = df.loc[df.index < '01-01-2015']
test = df.loc[df.index >= '01-01-2015']

fig, ax = plt.subplots(figsize=(15, 5))
train.plot(ax=ax, label='Training Set', title='Data Train/Test Split')
test.plot(ax=ax, label='Test Set')
ax.axvline('01-01-2015', color='black', ls='--')
ax.legend(['Training Set', 'Test Set'])
plt.show()
```
![screen-shot3](screen-shot3.png)
