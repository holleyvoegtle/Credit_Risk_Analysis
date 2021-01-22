# Credit_Risk_Analysis

## Overview

The purpose of this module was to build skills in data preparation, statistical reasoning, and machine learning through a real-world challenge: credit card risk. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. For this, different techniques were used to train and evaluate models with unbalanced classes. Imbalanced-learn and scikit-learn libraries were employed to build and evaluate models using resampling.

For this analysis, a dataset from LendingClub (peer-to-peer lending services company) was obtained from a csv file. The data was oversampled using RandomOverSampler and SMOTE algorithms and under sampled using the ClusterCentroids algorithm.  The next thing, a combinatorial approach of over- and under sampling using the SMOTEENN algorithm was used. Then, two new machine learning models the reduce bias: BalancedRandomForestClassifier and EasyEnsembleClassifier were used to predict credit risk. The final results of these test are summarized below. 	


## Results

**Oversampling**

Native Random Oversampling
- The accuracy score is .65
- The precision for high risk is low and low risk is high indicating an overfitting for the low risk.
- The recall score for both cases are not ideal
![](https://github.com/holleyvoegtle/Credit_Risk_Analysis/blob/main/images/fig1_naive%20random.png)

SMOTE
- The accuracy score is .63 
- The precision is the same as above.
- The recall score is lower than the naive random and is also not good.
![](https://github.com/holleyvoegtle/Credit_Risk_Analysis/blob/main/images/fig2_SMOTE.png)


**Undersampling(ClusterCentroids)**

- The accuracy score is .51 which is even lower than the first two oversampling
- The precision for high risk and low risk are also .01 and 1.00 which means that there is also overfitting for the data
- The recall score for low risk is even lower (.42) than the oversampling where the high risk is about the same.
![](https://github.com/holleyvoegtle/Credit_Risk_Analysis/blob/main/images/fig3_undersampling.png)

**Combination (over and Under) Sampling**

SMOTEEN
- The accuracy score is also low with .51
- The precision for high and low risk is also the same as the under and over sampling
- The recall is slightly higher for high risk at .70 and sightly lower for low risk at .57
![](https://github.com/holleyvoegtle/Credit_Risk_Analysis/blob/main/images/fig4_SMOTEEN.png)

**Ensemble**

Balanced Random Forest Classifier
- The accuracy is higher than the others with .78
- The precision is almost the same for high and low risk at .04 and 1.00
- The recall for high and low risk are at .67 and .91. Better for the high risk than the other models for far.
![](https://github.com/holleyvoegtle/Credit_Risk_Analysis/blob/main/images/fig5_balancedRandom.png)

Easy Ensemble Classifier
- The accuracy is the highest we have seen at .93
- The precision is slightly higher at .07 for high risk but the same for low risk at 1.00
- The recall for both high and low risk are the best we have seen at .91 and .94
![](https://github.com/holleyvoegtle/Credit_Risk_Analysis/blob/main/images/fig6_easy%20ensemble.png)

## Summary
Overall, the best results were from the Easy Ensemble Classifier. Not only was the accuracy the highest but so was the recall scores (sensitivity). Since credit risk is being analyzed here, it is more important to have better sensitivity than precision to detect fraudulent transactions. 

