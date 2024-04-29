# Forecasting 

**Model used to forecast reach** - 
  * Multi variate linear regression 
  * ANN (Artificial Neural Network) 
 

 **Reason why tree based model like random forest, decision tree, XgBoost couldn’t use in this model** -  

1. Chance of any impact of unit change in impression/budget on target data reach is less. Because unit change in impression may not be leading to different path to leaf node in tree. 

2. Extrapolation/interpolation  – in tree based algorithm extrapolation is not possible. 

Now for example , it needs to be explored if for a particular channel 90% of total budget is allocated , then what will be the reach.

Now , if budget is increased for a particular year or product, there is no historical data of that much budget, so tree based model will not be able to predict correctly.

For example like , if one predicting variable and one target variable there. 

Now, in historical data, maximum value of predicting variable is 100. Now for predicting variable 100, 200, 300 for all same forecasting target variable will come. 

It will be saturated. 

Now our objective is to find saturation point, we are looking for the saturation point from data, reality how business/reach work. Not the saturation because of model we used.  

Business will not be able to explore with various budget. They can’t plan budgeting. They can’t explore how reach will be ,with more budget. 




**Reason why linear regression, ANN used for forecasting** -

Above mentioned problem is not there in linear regrssion and ANN. 




**Model performance evaluation** - 

Performance metric used - **MAPE (Mean Absolute Percentage Error)**


Mape is used here as we can have comparison of 3 model for 3 channels. Mape will come like in %. 

Like 15% , mean on average 15% deviation there between actual and forecasted. 

So, we can compare 3 model , like for channel 1, channel 2,channel 3 corresponding mape value are 0.15,0.10,0.12.

So, almost similar are all model from performance perspective.

Mape is not data scale specific. But other metrics like mae, mse, rmse all are data scale specific. 

And data/ reach for differents channel are at different scale , so if I used those metrics then can’t compare whether all are similar or huge difference there in performance. 
We need to combined result of 3 channels' forecastings to get combined reach , Now one channel's forecasting is good , other's not so good, that's not expected. 

So, all model's performance identical is good. 


