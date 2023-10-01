# fraud-transaction-detection
Fraud transaction detection using Machine Learning algorithms on highly imbalanced dataset using ANN, Random Forest Classifier and XGBoost Classifier

## Observations
* The dataset is highly imbalanced, with only 0.129% of observations being fraudulent.
* There is no missing data in the dataset
* The dataset consists of 11 features which needed to be transformed

## Checking for multi-collinearity
![Correlation Heatmap](https://github.com/xecyborg/fraud-transaction-detection/blob/main/corr_heatmap.png)
## Summary and Explanation
* **oldbalanceOrg** and **newbalanceOrg** are perfectly correlated because these two columns represent the original and new balances in the sender's account after the transaction.
* **oldbalanceDest** and **newbalanceDest** are also perfectly correlated because these two columns represent the original and new balances in the recipient's account
* **nameOrig** and **nameDest** are mass categorical variable

## Action
1. Removing **newbalanceOrig** and **newbalanceDest** to avoid multicollinearity
2. Removing **nameOrig** and **nameDest** because of irrelavnce

### Weight of the balanced dataset
After applying Undersampling and then Oversampling the following are the weights of the new dataset :
> * Fraudulant transaction weight: 0.3335339444434781
> * Non-Fraudulant transaction weight: 0.6664660555565219

# ANN Loss Chart
![Loss Chart](https://github.com/xecyborg/fraud-transaction-detection/blob/main/loss_chart.png)

## ANN Performance
![ANN performance](https://github.com/xecyborg/fraud-transaction-detection/assets/103058112/fe6bf39d-6fde-413a-900f-6be3bd9b763b)


## Random Forest Performance
![RF Performance](https://github.com/xecyborg/fraud-transaction-detection/assets/103058112/b2b415ae-09c1-4bd7-8add-c8804155fd84)


## XGBoost Performance
![XGBoost Performance](https://github.com/xecyborg/fraud-transaction-detection/assets/103058112/8ce78493-a68f-490c-b655-58d0f383cd19)


## Model Performance Comparison

**ANN_model (Artificial Neural Network):**

> * F1-score on the training set: 0.9500
> * F1-score on the test set: 0.9493

**Random Forest:**

> * F1-score on the training set: 1.0 (perfect score)
> * F1-score on the test set: 0.9992

**XGBoost:**

> * F1-score on the training set: 0.9967
> * F1-score on the test set: 0.9963

![Model Comparison](https://github.com/xecyborg/fraud-transaction-detection/blob/main/model_comparison.png)

## Conclusion
Random Forest Model works best

