# Context

A data set describing the sale of individual residential property in Ames, Iowa from 2006 to 2010. 
The data set contains 2930 observations and a large number of explanatory variables 
(23 nominal, 23 ordinal, 14 discrete, and 20 continuous) involved in assessing home values.
You can also read about the different columns in the data [here](https://s3.amazonaws.com/dq-content/307/data_description.txt).

# Objective

We will transforming and selecting features to train and test a model to best predict potential housing prices in the future.

# Process

First, we feature engineer by:
- dropping any column with 5% null values.
- dropping any text column with any null values.
- fill in remaining null values with the most common value for the column.
- create new features (columns) that will help our model.
- drop any column that may leak future information or isn't useful.

Next, we select the features for our model learning by:
  - creating a correlation matrix
  - dropping all column that has less than 40% correlation to the target column `SalePrice`.
  - create dummy columns from all categorical features.
  
Lastly, we train and test our model.
We use Root Mean Squared Error(RMSE) as our error indicator. 
We select Linear Regression as our model and K-Fold of 5 for validation.

# Results

We received a RMSE of 57,008 without any feature selection and engineering.  
We received a RMSE of 55,275 after only feature engineering.   
Lastly, we received a RMSE of 33,327 after we implemented both feature engineering and feature selection.

Further optimization can be done for both feature engineering and feature selection with domain knowledge to lower the RMSE.
