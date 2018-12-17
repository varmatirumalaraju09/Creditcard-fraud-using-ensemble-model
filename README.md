# Creditcard-fraud-using-ensemble-model
**Project to detect credit card fraud detection using ensemble model**



The first industries to use data analysis techniques to prevent fraud were telephone companies, insurance companies and banks. 
Retail industries also suffer from fraud at POS.
Research is showing that internet transaction fraud is 10 times higher than in-store fraud.



Credit card fraud is a wide-ranging term for theft and fraud committed using or involving a payment card, such as a credit card or debit card, as a fraudulent source of funds in a transaction.
The purpose may be to obtain goods without paying, or to obtain unauthorized funds from an account. 
Credit card fraud is also an adjunct to identity theft.



## Disadvantage of Traditional Methods to detect fraud


### Occurrence of false positives: 
There will be high rates of false positive if the employees reject every transaction above a certain risk threshold. It not only affects the sale in the process, but also lifetime value generated from the customer.


### The card data used is legitimate but not under the consent of the owner:
Criminal gangs use malware and phishing emails as a means to compromise customers’ security and personal details. Once obtained, the details will be used to access customer accounts or to commit fraud. 


## Why Machine Learning in this scenario?

Machine learning algorithms are able to detect and recognize thousands of patterns on a user’s purchasing journey instead of the few captured by creating rules. 
Fraud can be predicted in a large volume of transactions by applying cognitive computing technologies to raw data.
Other influencing factors are its
speed, 
scale and efficiency.


## About the data

The credit card data has been obtained from kaggle and the data contains around 280k bank transactions. It's features, being personal data, have been transformed using PCA into integers. The features include amount the transaction, class (0 - normal transaction, 1- Fraud transaction) and the time of the transaction. All the other features are transformed.


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/data_credit.png)


Correlation plot of the features is like,


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/credit_correlation.png)


The correlation is -1 and the line is descending which means there is strong negative linear relationship between the features.


A boxplot of the transaction amount classified using the class variable is like,


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/credit_boxplot.png)


Once the preprocessing and EDA are done, we built a random forest model using the train data. The data has been split into train-test in 70-30 split. For the project, since our data is biased, we use the metric AUC to find how good the model is. The area under the curve for the random forest built with the train data is 0.852.


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/Randomforest.png)


We built another model using rpart and checked the AUC in this case. It is 0.908.

![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/rpart.png)



## Feature Importance

Using the varImpPlot and the random forest, feature importance has been done.


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/Featureimportance.png)


## Sampling

Since our data is imbalanced, we tried sampling the data. We did undersampling, oversampling, both and ROSE (Sythetic data built by rose function which uses algorithms internally to build the data). After sampling, we checked AUC for rpart model and random forest for all kinds of sampled data. The best result is from the ROSE data.

![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/rose.png)

## Building models using ROSE data.

We built random forest, rpart, knn and NaiveBayes models using the ROSE data and calculated AUC in every case.

### RPART


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/rose_rpart.png)


### Random Forest


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/rose_randomforest.png)


### KNN


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/rose_knn.png)


### Naive Bayes

![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/rose_naive.png)


## Superlearner

Superlearner is a package that provides easy way to create machine learning ensembles with the use of the high-level functions by offering a standardized wrapper to fit an ensemble. Using Superlearner,


- Simply add algorithms and fit the ensemble.
- Automatically estimate the weights of the models.
- Remove models that don’t contribute to model prediction.	

Superlearner's wrapper is like,


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/Wrappers.png)


This has list of models that can be built using the superlearner. Required models need to be just added to the library used in the superlearner's syntax.


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/superlearner.png)

The ensembling took around 3 hrs and its result is like,


![Markdown Logo](https://github.com/abhi19071993/Creditcard-fraud-using-ensemble-model/blob/master/superlearner_result.png)



The AUC of our ensemble model is 0.949.


So we built a model which is around 95% good in predicting.












