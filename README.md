# In-class-Kaggle-competition: Project Overview
* Created a model that predicts whether an online jewerly shop visitor will purchase an item from the shop, to help shop owner improve customer relationship management(CRM) by understanding customer's purchasing behaviour and loyalty.
* Engineered features from browsing data.
* Optimized Logistic Regression, Decision trees, XGBoost, LGBM using GridsearchCV to reach the best model. 

## Trouble viewing jupyter notebook on Github?
1) Open https://nbviewer.jupyter.org/.
2) Paste in the URL of the desired notebook.

## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn

## Data
Data is provided by Kaggle. We have the following features:
* ID
* Administrative
* Administrative_Duration
* Informational
* Informational_Duration
* ProductRelated
* ProductRelated_Duration
* BounceRates
* ExitRates
* PageValues
* SpecialDay
* Month
* OperatingSystems	
* Browser
* Region	
* TrafficType
* VisitorType
* Weekend
* Revenue

## EDA
Let's take a look at the distribution of data, value counts and correlation between features. Below are the highlights.

![alt text](https://github.com/phoebecmk/In-class-Kaggle-competition/blob/EDA_improvement/Github%20README/rev.PNG)
Response variable is not 50/50 so the dataset is imbalanced.

![alt text](https://github.com/phoebecmk/In-class-Kaggle-competition/blob/EDA_improvement/Github%20README/corr.PNG)
Some variables are highly correlated. Decision trees might perform better in this dataset

![alt text](https://github.com/phoebecmk/In-class-Kaggle-competition/blob/EDA_improvement/Github%20README/rates.PNG)

## Data Preprocessing
After taking a look at the dataset, I cleaned it up so it's usable for the model. 
* Created average duration in each webpage
* Changed variable type
* normalized numerical variables

## Model Building

I tried using oversampling/undersampling to balance the data but it resulted in worse accuracy.

I split data into train and test set with 25% test size, and later on tried training on folds.

I tried 4 models and evaluated them using AUC, as specified in Kaggle competition. If I had the flexibility to choose the metric, I would consider F1 score or Kappa which are suitable for unbalanced dataset.

Here are the four models:
* Logistic regression - Baseline model
* Random Forest - because it works well with unbalanced data
* LGBM, XGBoost - works great with dataset with a mix of numerical and categorical variables, increase in predictive accuracy and speed.

## Model Performance
* Logistic regression - 80%
* Random Forest - 89%
* LGBM, XGBoost - AUC 93%

## Thoughts on future improvements
* Build a flask API endpoint host on heroku for better usability
