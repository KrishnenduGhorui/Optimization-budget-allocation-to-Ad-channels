# Optimization of Budget allocation to number of advertisement channels :

Developing an optimization system with ML model and optimization algorithm that will suggest optimized budget to be allocated to different channels, so that combined de-duplicated reach will be maximum.

Tools/Technologies Used: Python, GCP, BigQuery, Looker studio. Machine Learning, Google cloud storage bucket etc.

Role & resposibility - 

•Loaded data from BigQuery to jupyter notebook on GCP Vertex AI.
•Performed feature selection, feature engineering. Handled missing data, outlier, pre-processed data by Python, pandas, Encoded categorical data by Target encoding.
•Performed EDA from various business point of view.
•Built and trained several ML models (OLS Regression Model, Ridge Regression, Random Forest Regression) for each channel individually with separate individual data.
•Evaluated performance of regression model by metrics like R2 score, adjusted R2 score, MAPE.
•Performed all above steps for data of 3 channels separately.
•Calculated combined reach with predicted individual reach of all channels by using Sainsbury formula (de-duplicated the combined reach with de-duplication factor).
•Optimized budget allocated to each channel to have maximum combined reach, with some constraints.
•Created MVP by a pipeline – Uploading input data on google cloud bucket will trigger the pipeline to run. Pipeline will load input data to python script from cloud bucket, run forecasting, optimization, save the optimized output result to BigQuery table, from there output is visualized in Looker studio. 



Sainsbury formula - 
RChnl1 + RChnl2 – (K* RChnl1* RChnl2)
