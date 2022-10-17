# Credit Risk Analysis

## Overview of Project
Jill commends you for all your hard work. Piece by piece, you’ve been building up your skills in data preparation, statistical reasoning, and machine learning. You are now ready to apply machine learning to solve a real-world challenge: credit card risk.

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, you’ll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks you to use `imbalanced-learn` and `scikit-learn` libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, you’ll oversample the data using the `RandomOverSampler` and `SMOTE` algorithms, and undersample the data using the `ClusterCentroids` algorithm. Then, you’ll use a combinatorial approach of over and undersampling using the `SMOTEENN` algorithm. Next, you’ll compare two new machine learning models that reduce bias, `BalancedRandomForestClassifier` and `EasyEnsembleClassifier`, to predict credit risk. Once you’re done, you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

## Deliverables:
This new assignment consists of three technical analysis deliverables and a written report.

1. ***Deliverable 1:*** Use Resampling Models to Predict Credit Risk
2. ***Deliverable 2:*** Use the SMOTEENN Algorithm to Predict Credit Risk
3. ***Deliverable 3:*** Use Ensemble Classifiers to Predict Credit Risk
4. ***Deliverable 4:*** A Written Report on the Credit Risk Analysis [README.md](https://github.com/emmanuelmartinezs/Credit_Risk_Analysis)

# Deliverable 1:  
## Use Resampling Models to Predict Credit Risk 
### Deliverable Requirements:

Using your knowledge of the `imbalanced-learn` and `scikit-learn` libraries, you’ll evaluate three machine learning models by using resampling to determine which is better at predicting credit risk. First, you’ll use the oversampling `RandomOverSampler` and `SMOTE` algorithms, and then you’ll use the undersampling `ClusterCentroids` algorithm. Using these algorithms, you’ll resample the dataset, view the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

#### Deliverable 1 Requirements

For all three algorithms, the following have been completed:
- An accuracy score for the model is calculated
- A confusion matrix has been generated
- An imbalanced classification report has been generated 


# Deliverable 2:  
## Use the SMOTEENN algorithm to Predict Credit Risk 
### Deliverable Requirements:

Using your knowledge of the `imbalanced-learn` and `scikit-learn` libraries, you’ll use a combinatorial approach of over and undersampling with the `SMOTEENN` algorithm to determine if the results from the combinatorial approach are better at predicting credit risk than the resampling algorithms from Deliverable 1. Using the `SMOTEENN` algorithm, you’ll resample the dataset, view the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

#### Deliverable 2 Requirements

The combinatorial SMOTEENN algorithm does the following:
- An accuracy score for the model is calculated
- A confusion matrix has been generated
- An imbalanced classification report has been generated  


# Deliverable 3:  
## Use Ensemble Classifiers to Predict Credit Risk 
### Deliverable Requirements:

Using your knowledge of the `imblearn.ensemble` library, you’ll train and compare two different ensemble classifiers, `BalancedRandomForestClassifier` and `EasyEnsembleClassifier`, to predict credit risk and evaluate each model. Using both algorithms, you’ll resample the dataset, view the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

#### Deliverable 3 Requirements

The `BalancedRandomForestClassifier` algorithm does the following:
- An accuracy score for the model is calculated 
- A confusion matrix has been generated 
- An imbalanced classification report has been generated 
- The features are sorted in descending order by feature importance

The `EasyEnsembleClassifier` algorithm does the following:
- An accuracy score of the model is calculated 
- A confusion matrix has been generated 
- An imbalanced classification report has been generated  


### DELIVERABLE RESULTS:
Below are the results from the various techniques used to predictive model for High-Risk loans.  


**Naive Random Oversampling:**  

![d1](https://github.com/ZZaman1989/Credit_Risk_Analysis/blob/main/Resources/Naive.png)

**SMOTE:**  

![d1](https://github.com/ZZaman1989/Credit_Risk_Analysis/blob/main/Resources/SMOTE.png)

**ClusterCentroids:**  

![d1](https://github.com/ZZaman1989/Credit_Risk_Analysis/blob/main/Resources/Cluster.png)

**Smoteen:**  

![d1](https://github.com/ZZaman1989/Credit_Risk_Analysis/blob/main/Resources/Smoteen.png)


**BalancedRandomForestClassifier:**  

![d1](https://github.com/ZZaman1989/Credit_Risk_Analysis/blob/main/Resources/Balance%20Random%20Forest%20Classifier.png)

**Easy Ensemble AdaBoost Classifier:**

![d1](https://github.com/ZZaman1989/Credit_Risk_Analysis/blob/main/Resources/East%20Ensemble%20AdaBoost%20Classifier.png)

## SUMMARY

Utlizing **EasyEnsembleClassifier** is the most effective. Provides a highest Score for all Risk loans.
In General, above the 90% of the current analysis, utlizing **EasyEnsembleClassifier** will perform a High-Risk loan precision as a great value for the overall analysis. 