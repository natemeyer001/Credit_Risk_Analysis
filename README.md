# Credit_Risk_Analysis

## Overview
Use multiple machine learning algorithms to asses credit risk. Then compare the results and recommend an algorithm to use, if any are acceptable.

## Background Info
The majority of the credit risk data consists of good loans, which makes it an inherently unbalanced dataset, but that can be adjusted for. The first way is to oversample, which selects more instances from the minority class, bad loans, until it is closer (or eqaul) to the majority class. The second approach is to undersample, which selects fewer instances from the majority class until the two classes are balanced. The final approach is a combination of oversampling and undersampling.

## Results
The first model was a Naive Random OverSampler, which had a balanced accuracy score of 0.649. Below is the imbalanced classification report:
![naive_oversampling](https://user-images.githubusercontent.com/30487641/140828988-6b558e40-4898-4380-8967-280c14822990.PNG)


The second model was a SMOTE Oversampler, which had a balanced accuracy score of 0.658 and below is the imbalanced classification report:
![SMOTE_oversampling](https://user-images.githubusercontent.com/30487641/140829155-e1791e9a-47f7-4335-a3f6-a1192e36ce70.PNG)


The third model was a Cluster Centroid Resampler, which undersampled the data. The balanced accuracy score was 0.658.
![cluster_centroid_undersampling](https://user-images.githubusercontent.com/30487641/140829422-e05a1335-b046-48da-b8d1-69daf9797bc8.PNG)


The fourth model was a SMOTEENN Combination, which had a balanced accuracy score of 0.544.
![SMOTEENN_combination](https://user-images.githubusercontent.com/30487641/140829588-1fc03509-4c69-4ae1-9377-54f4c9510208.PNG)


The final two were Ensemble Leaners, with Balanced Random Forest Classifier first. The accuracy score was 0.789.
![random_forest](https://user-images.githubusercontent.com/30487641/140829778-0173e239-8651-4f83-a29e-097c39b31871.PNG)


The last model was an AdaBoost Classifier and the balanced accuracy score was 0.915.
![ada_boost](https://user-images.githubusercontent.com/30487641/140829841-3876a1f9-2259-413e-9878-1c0f4296d6c4.PNG)



## Conclusion
The accuracy score 






