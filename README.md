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
