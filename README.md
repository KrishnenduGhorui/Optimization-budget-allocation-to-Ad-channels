# Optimization of Budget allocation to number of advertisement channels :

### Objective - 
Build a Cross Channel Ad Reach OptimizationEngineto determine optimized budget splitacross media channels to obtain the maximum campaign reach for a given totalcampaign budget, campaign conditions and target audience

### Impact –
**Reach improvement**: Improved cross-channel dedupedreach by 7% (average on recent 20 campaigns) compared tonon-optimised budget allocation, driving significant MROI (MarketingReturn on Investment) improvementon advertiser side.
**Clearanceon attribute that affect Reach** - developed a full picture of understanding of the attribute of campaigndata and target audience with a list of indicated investment areas to improve overallreach over time. 

## Steps:·      
1. Collected data from bigquery table. ·
2. Pre-processed data like missing data handling,outlier handling, data transformation, data encoding(by target guided encoding)and performed feature engineering and feature selection (using VIF score, correlation,variance threshold, and wrapper method ……, ·
3. Forecast reach for each channel by Multi-variatelinear regression & ANN, evaluated forecasting by adjusted R2 score,MAPE. Then combined them to get overall de-duped reach by Sainsbury formulausing de-duplication factor. ·
4. Constrained Optimization of budget split acrosschannels is done to have highest possible de-duped reach using brute force techniques.

## Model performance –
AdSmart - R-Score- 0.89 & MAPE of 0.21 , on test data set covering 5037 campaigns  

**Three advertising channel platform are there**
* AdSmart – Tv Channel 
* VoD( Video on Demand) – YouTube , Netflix, Amazon Prime,Disney +hotstar 
* Digital – Social media (Facebook , twitter, Instagrams), GoogleAdSense on browser, blog, mobile app

**De-duplication process using Sainsbury formula** –
Reach for channel 1, channel 2, channel 3 are R<sub>1</sub>,R<sub>2</sub>,R<sub>3</sub> respectively. 
K<sub>1</sub> , K<sub>2</sub> are de-duplication factor. 

R<sub>de-duped1</sub>=R<sub>1</sub>+R<sub>2</sub> - K<sub>1</sub>*R<sub>1</sub>*R<sub>2</sub>
R<sub>de-duped</sub>= R<sub>de-duped1</sub> + R<sub>3</sub>- K<sub>2</sub>* R<sub>de-duped1</sub>*R<sub>3</sub> 

K<sub>1</sub>=1.02, K<sub>2</sub>=1.11



K<sub>1


</sub>






•Created MVP by a pipeline – Uploading input data on google cloud bucket will trigger the pipeline to run. Pipeline will load input data to python script from cloud bucket, run forecasting, optimization, save the optimized output result to BigQuery table, from there output is visualized in Looker studio. 



Tools/Technologies Used: Python, GCP, BigQuery, Looker studio. Machine Learning, Google cloud storage bucket etc.

Sainsbury formula - 
RChnl1 + RChnl2 – (K* RChnl1* RChnl2)
