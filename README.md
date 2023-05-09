# Credit_Risk_Analysis

## Overview
We will be using resampling to build and evaluate different models predicting credit risk, because there is a large imbalance between good loans and risky loans. Using a credit card dataset we'll oversample with RandomOverSampler and SMOTE, undersample with ClusterCentroids, over-and-undersample with SMOTEENN, and also use BalnacedRandomForestClassifier and EasyEnsembleClassifier to reduce bias. Then we'll be able to assess the accuracy, percision, and recall of each model.

## Results
### Random Oversampler Algorithm
<img src="images/naive_random_oversampling.PNG" width="700">

- The Balanced Accuracy Score is 64.1%.
- High-risk precision is low at 1% with a sensitvity of 60%.
- Low-risk precision is 100%, due to the large number of low-risk loans, and has a sensitivity of 68%.

### Oversampling SMOTE Algorithm
<img src="images/smote_oversampling.PNG" width="700">

- The Balanced Accuracy Score is about the same at 63.7%.
- The high-risk precision and sensitivity stay the same at 1% and 60% respectively.
- Low-risk precision and sensitivity also stays the same at 100% and 68% respectively.

### Undersampling Cluster Centroids Algorithm
<img src="images/undersampling.PNG" width="700">

- The Balanced Accuracy Score decreased quite a bit using undersampling resulting in 51.6%
- The high-risk precision and sensitivity stayed the same as both oversampling algorithms at 1% and 60% respectively.
- Low-risk precision stayed the same as the first 2 algorithms at 100% but the sensitivity decreased 43%.

### Combination Sampling SMOTEENN Algorithm
<img src="images/combination_sampling.PNG" width="700">

- The Balanced Accuracy Score was similar to the oversampling models at 63.8%.
- The precision of both high-risk and low risks remain at 1% and 100% respectively.
- The sensitivity of the high-risk was a little higher than the oversampling algorithms coming in at 70%.
- The low-risk sensitivity of 57% was higher than the undersampling alogrithms but slightly lower than the oversampling alogrithms.

### Balanced Random Forest Classifier Algorithm
<img src="images/balanced_random_forest_classifer.PNG" width="700">

- The Balanced Accuracy Score increased to 78.8% using the Balanced Random Forest Classifier.
- The high-risk precision increased to 4%, with the low-risk precision remaining at 100%.
- The high-risk sensitivity was 67% which very similar to the SMOTEENN and oversampling algorithms.
- The low-risk sensitivity increased significantly to 91% compared to all previous algorithms.

### Easy Ensemble Classifier Algorithm
<img src="images/easy_ensemble_adaboost_classifier.PNG" width="700">

- The Balanced Accuracy Score is at it's highest, 92.5%, when using the Easy Ensemble Classifier.
- The high-risk precision increases again to 7%, with the low-risk continuing to remain at 100%.
- Both the high-risk and low-risk sensitivity see their highest precentages at 91% and 94% respectively.

## Summary
All the models show weak percision when predicting if the credit risk is high. The Easy Ensemble Classifier model clearly provides the best sensitivity percentages for predicting high risk loans and predicting low-risk loans, which means that high-risk loan prediction is likely correct when made but the even the Easy Ensemble Classifier Model only resulted in a 7% percision for predicting high-risk loans, meaning it's still sending a lot of false positive high-risk loans which could be bad for the bank's business opportunities.

I wouldn't recommend solely using one of these models to predict high-risk loans. But, if the Easy Ensemble Classifier model was used as a preliminary step to speed up those that are likely to be low-risk and then have those marked high-risk assessed by a loan professional, the model could increase the efficiency of assessing the credit risk.

