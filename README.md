# Credit_Risk_Analysis

## Overview

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersampled the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over and under sampling using the SMOTEENN algorithm. Finally, I compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 

## Results

### Oversampling
In this section, I compared two oversampling algorithms to determine which algorithm results in the best performance. I oversampled the data using the naive random oversampling algorithm and the SMOTE algorithm.

#### Naive Random Oversampling Results
|             | pre  | rec  | spe  |  f1  | geo  | iba  |  sup  |
| ----------- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| high_risk   | 0.01 | 0.69 | 0.58 | 0.02 | 0.63 | 0.40 |   101 |
| low_risk    | 1.00 | 0.58 | 0.69 | 0.73 | 0.63 | 0.39 | 17104 |
| avg / total | 0.99 | 0.58 | 0.69 | 0.73 | 0.63 | 0.39 | 17205 |

#### SMOTE Oversampling Results
|             | pre  | rec  | spe  |  f1  | geo  | iba  |  sup  |
| ----------- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| high_risk   | 0.01 | 0.63 | 0.69 | 0.02 | 0.66 | 0.44 |   101 |
| low_risk    | 1.00 | 0.69 | 0.63 | 0.82 | 0.66 | 0.44 | 17104 |
| avg / total | 0.99 | 0.69 | 0.63 | 0.81 | 0.66 | 0.44 | 17205 |

### Undersampling
In this section, I tested an undersampling algorithms to determine which algorithm results in the best performance compared to the oversampling algorithms above.

#### Undersampling Results
|             | pre  | rec  | spe  |  f1  | geo  | iba  |  sup  |
| ----------- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| high_risk   | 0.01 | 0.69 | 0.40 | 0.01 | 0.52 | 0.28 |   101 |
| low_risk    | 1.00 | 0.40 | 0.69 | 0.57 | 0.52 | 0.27 | 17104 |
| avg / total | 0.99 | 0.40 | 0.69 | 0.56 | 0.52 | 0.27 | 17205 |

### Combination (Over and Under) Sampling
In this section, I tested a combination of over and under sampling algorithms to determine if the algorithm results is the best performance compared to the other sampling algorithms above.

#### Combination Results
|             | pre  | rec  | spe  |  f1  | geo  | iba  |  sup  |
| ----------- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| high_risk   | 0.01 | 0.72 | 0.58 | 0.02 | 0.65 | 0.42 |   101 |
| low_risk    | 1.00 | 0.58 | 0.72 | 0.73 | 0.65 | 0.41 | 17104 |
| avg / total | 0.99 | 0.58 | 0.72 | 0.73 | 0.65 | 0.41 | 17205 |

### Ensemble Learners
In this section, I compared two ensemble algorithms to determine which algorithm results in the best performance. I trained a Balanced Random Forest Classifier and an Easy Ensemble AdaBoost classifier.

#### Balanced Random Forest Classifier Results
|             | pre  | rec  | spe  |  f1  | geo  | iba  |  sup  |
| ----------- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| high_risk   | 0.03 | 0.70 | 0.87 | 0.06 | 0.78 | 0.60 |   101 |
| low_risk    | 1.00 | 0.87 | 0.70 | 0.93 | 0.78 | 0.62 | 17104 |
| avg / total | 0.99 | 0.87 | 0.70 | 0.93 | 0.78 | 0.62 | 17205 |

#### Easy Ensemble AdaBoost Classifier Results
|             | pre  | rec  | spe  |  f1  | geo  | iba  |  sup  |
| ----------- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| high_risk   | 0.09 | 0.92 | 0.94 | 0.16 | 0.93 | 0.87 |   101 |
| low_risk    | 1.00 | 0.94 | 0.92 | 0.97 | 0.93 | 0.87 | 17104 |
| avg / total | 0.99 | 0.94 | 0.92 | 0.97 | 0.93 | 0.87 | 17205 |

## Summary:
First glance shows "Easy Ensemble AdaBoost Classifier" with promising results, but further information about business priorities is needed for a definitive answer. My analysis summarizes the 2 most relevant categories: Precision Rates and Recall Rates.

### Precision Rates
Low risk precision rates were 100% across all results, and High risk precision rates were varied from 1% to 9%. Easy Ensemble AdaBoost Classifier showed a clear advantage in high risk precision at 9% and tied with the other results for the low risk precision at 100%.

### Recall Rates
Low risk recall rates were 40% to 94%, and High risk recall rates were 63% to 92%. Easy Ensemble AdaBoost Classifier had the highest average recall rates, and Undersampling had the lowest average recall rates.




