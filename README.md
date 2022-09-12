### Credit_Risk_Analysis

## Analysis Overview

In this project, we use Python generate several machine learning models to train and evaluage models with unbalanced classes. 
We will use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.
We adopted the following procedure:

- Using the credit card credit dataset from LendingClub we:
    - Oversampled the data using the RandomOverSampler and SMOTE algorithms.
    - Undersample the data using the ClusterCentroids algorithm.
    - Use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm.
    - Compare two machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier.
We will evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk or not.

## Results

By using Machine Learning to resample the dataset using Python libraries: scikit-learn and imbalanced-learn, we evaluated the results and provided a comparison for our analysis below.

From the original dataset of loan applications in Q1 of 2019. We used the "loan status" to determine whether the application was considered "low" or "high" risk. Applications that had "current" as the "loan status" were classified as "low risk" and the remaining, including: 'Late (31-120 days)', 'Late (16-30 days)', 'Default', and 'In Grace Period' were classified as "high risk". This reduced the dataset to 68,817 total applications with 68,470 classified as "low risk" and 347 classified as "high risk".

# Use Resampling Models to Predict Credit Risk

# Using RandomOverSampler Model

- Balanced Accuracy score of 63.8%.
- "High Risk" precision rate of only 1% with the recall at 61% giving this model an F1 score of 2%. 
- "Low Risk" precision rate of 100% and recall of 61%.

# Using SMOTE Model

- Balanced Accuracy score of 65.8%.
- "High Risk" precision rate of only 1% with the recall at 62% giving this model an F1 score of 2%. 
- "Low Risk" precision rate of 100% and recall of 69%.

# Using Cluster Centroids Model for Undersampling

- Balanced Accuracy score of 65.9%.
- "High Risk" precision rate of only 1% with the recall at 69% giving this model an F1 score of 1%. 
- "Low Risk" precision rate of 99% and recall of 40%.

# Using a Combination (Over and Under) Sampling

- Balanced Accuracy score of 54.5%.
- "High Risk" precision rate of only 1% with the recall at 72% giving this model an F1 score of 2%. 
- "Low Risk" precision rate of 99% and recall of 69.57%.

# Using Balanced Random Forest Classifier Model

- Balanced Acuracy score of 78.85%
- "High Risk" precision rate of 9% with the recall at 92% giving this model an F1 score of 16%. 
- "Low Risk" precision rate of 100% and recall of 94%.

# Using Easy Ensemble Clasifier Model

- Balanced Acuracy score of 93.16%
- "High Risk" precision rate of 9% with the recall at 92% giving this model an F1 score of 16%. 
- "Low Risk" precision rate of 99% and recall of 94%.

## Results

In reviewing all six models, the EasyEnsembleClassifer model yielded the best results with an accuracy rate of 93.16% and a 9% precision rate when predicting "High Risk candidates. The sensitivity rate (aka recall) was also the highest at 92% compared to the other models. The result for predicting "Low Risk" was also the highest with the sensitivity rate at 94% and and a reacall score of 94%. Therefore, if a model needed to be recommended to perform this type of analysis, then this one would be the clear choice.

Something to take notice of should be that from the original dataset the ones taken for this analysis had 99% of the applications classified as "Low Risk" with only 1% of the data classified in the "High Risk" category. This may cause the results to skew greatly as there is a risk that the Machine Learning algorithms are creating clusters drawing from too small of a dataset of actual "High Risk" applications. This margin of risk might not be something that banks would be comfortable accepting.