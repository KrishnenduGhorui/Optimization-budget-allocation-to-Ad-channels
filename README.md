# Optimization of Budget allocation to number of advertisement channels :

## Objective - 
Build a Cross Channel Ad Reach OptimizationEngineto determine optimized budget splitacross media channels to obtain the maximum campaign reach for a given totalcampaign budget, campaign conditions and target audience

## Impact –
**Reach improvement**: Improved cross-channel dedupedreach by **7% (average on recent 120 campaigns)** compared to non-optimised budget allocation, driving significant **MROI (Marketing Return on Investment) improvement** on advertiser side.

**Clearance on attribute that affect Reach** - developed a full picture of understanding of the attribute of campaign data and target audience with a list of indicated investment areas to improve overall reach over time. 

## Steps:·      
1. Loaded data from **BigQuery** to jupyter notebook on **GCP Vertex AI**.
2. Performed EDA from various business point of view.
3. Pre-processed data like missing data handling (Using **KNN imputation,MICE imputation**),outlier handling, data transformation, data encoding (by **target guided encoding**) and performed feature engineering and feature selection (using **VIF score, correlation,variance threshold, and wrapper method ……,**·
4. Trained **Multivariate linear regression & ANN model** for reach forecasting for each channel individually with separate individual data, evaluated model‘s performance by metrics like **R2 score, adjusted R2 score, MAPE**.
5. Then combined them to get overall de-duped reach by **Sainsbury formula** using de-duplication factor.
6. **Constrained Optimization** of budget split across channels is done to have highest possible de-duped reach using brute force techniques.

![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/1f044326-9257-4632-80e2-09f2c5f22fa1)

![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/601a07f2-4932-41b5-8915-b09274a0c78f)

## Three advertising channel platform are there
* AdSmart – Tv Channel 
* VoD( Video on Demand) – YouTube , Netflix, Amazon Prime,Disney +hotstar 
* Digital – Social media (Facebook , twitter, Instagrams), GoogleAdSense on browser, blog, mobile app

## Model performance –
* AdSmart - R-Score- 0.89 & MAPE of 0.21 , on test data set covering 5037 campaigns  
* VoD - R-Score- 0.85 & MAPE of 0.23 , on test data set covering 3289 campaigns 
* Digital - R-Score- 0.86 & MAPE of 0.21 , on test data set covering 3136 campaigns

## De-duplication process using Sainsbury formula –

Reach for channel 1, channel 2, channel 3 are R<sub>1</sub>,R<sub>2</sub>,R<sub>3</sub> respectively. 

K<sub>1</sub> , K<sub>2</sub> are de-duplication factor. 

R<sub>de-duped1</sub>=R<sub>1</sub>+R<sub>2</sub> - K<sub>1</sub>*R<sub>1</sub>*R<sub>2</sub>

R<sub>de-duped</sub>= R<sub>de-duped1</sub> + R<sub>3</sub>- K<sub>2</sub>* R<sub>de-duped1</sub>*R<sub>3</sub> 

K<sub>1</sub>=1.02, K<sub>2</sub>=1.11

![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/b21017e7-aa0d-47e6-8baf-e01b4c6739a5)


•Created a pipeline – Uploading input data on google cloud bucket will trigger the pipeline to run. Pipeline will load input data to python script from cloud bucket, run forecasting, optimization, save the optimized output result to BigQuery table, from there output is visualized in Looker studio. 



**Tools/Technologies Used:**  
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/d792e179-2ba0-43b4-be35-395141b09898)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/4233f446-7dd9-4045-be58-b2df8c3bca99)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/c9ed205f-f4d6-4664-ad16-f2b45ee92ef1)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/ba8f0672-7659-4c39-a94a-89f9a913ec30)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/0de6263d-8bc4-4bb5-a278-53e9fcdd3882)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/6b14bbcc-37b9-40d8-bd53-d85db8e7e30d)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/78a5c346-e1bd-414a-a4e7-d31fcf4cd262)
![image](https://github.com/KrishnenduGhorui/Optimization-budget-allocation-to-Ad-channels/assets/77465776/3207311d-c2f3-474b-8d0b-846ac9c084a5)





