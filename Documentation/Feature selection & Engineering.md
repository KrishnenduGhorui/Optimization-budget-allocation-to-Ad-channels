**Feature selection** - 

Total around 235 attributes were there in dataset. Among them only 20 attributes used for modelling. 

Attributes/feature selection done based on below -

* Correlation – Correlation of input feature with target feature, less correlated input features are removed. 

* VIF score – VIF score is more than 5 for pair of input feature, one of them which is less correlated to target is removed. 

* Missing data – feature having more than 50% missing data and not so important for target, are removed. Some record having target data missing are removed. 

* business concept – Based on business knowledge whatever attributes are not so important are removed. 

* Wrapper method Exhaustive feature selection techniue is used 


During modelling, based on p value also some features removed or added to model to have better model performance. (anova /chi square) 



Many records are excluded those have very important sensitive attributes missing, those shouldn’t be imputed by any means as those can mislead the prediction, training. (KNN imputation???)

Record removal steps and corresponding reason are visualized in waterfall chart. 


**Feature engineering -**


Campaign duration was one significant attribute for target data. So, in data campaign starting and end date was provided, so campaign duration calculated by taking its difference. 

Frequency is calculated by target impression divided by reach hh.





