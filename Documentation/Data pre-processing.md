**Missing data handling** - 

 Missing data handled by below mentioned way - 

* KNN imputation
* MICE (Multivariate Imputation by Chained Equations)/ Iterative Imputation 
* For some categorical missing data is replaced by a new category called ‘absent’ . 
  If any new category entered to that fetaure by user in future, that will be considered as ‘Others’ as well.
* Some records are direactly removed, those have very important sensitive attributes missing, those shouldn’t be imputed by any means or other way as those can mislead the prediction, training in case imputated value is not correct. 


**Scaling**  - 

* MinMax scaling 

**Transformation** - 

To have linear relationship with input feature and output target feature below transformation are done- 
 
* inverse exponential transformation. 
* Logarithmic transformation  

**Encoding on categorical attribute** - 

* Target guided mean encoding on categorical attributes 


Around 30 category there for attribute like industry. 
So, can’t do one hot encoding ,as that will increase the feature /column number. That’s not good from curse of dimensionality perspective.

Ordinal encoding can’t be done , as there is no specific order in industry, we can’t encode like computer industry as 1, media & entertainment as 2 , that doesn’t make sense. 

Label encoding also problem there, label encoding is done based on alphabet in ascending order, like category starting with A will get label as 1, starting with next alphabet ‘like’ C will get label as 2 , like this. 

In this way who will get 30 as label, that will get more weightage during model training. That should not happen. 

So, in target encoding is done, which category has more ferequency that will get rank 1.

**Inverse exponential transformation** – 

    (1-np.exp(-1*B*pow(data_val, C)))

B and C value taken after lot of trial and error method, finalizing curve coming saturated after a point of data.  



