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
The accuracy scores from the first four are quite worrisome, with all above 0.5 but the highest at 65.8% accuracy. It got much better with the Ensemble Learners, with AdaBoost having the best balanced accuracy score. 

All of the models had very good precision scores (i.e. how reliable a positive classificaion is) with the lowest being 0.99 for the avg/total. However, the precision of the high_risk was terrible across the board, with the first 4 models having 0.01, and the Ensemble Learners at 0.03 and 0.05 for Random Forest and AdaBoost respectively. The window dressing of the overall scores are appealing, but when you look closer, you see that the foundation is not sturdy with the tiny precision of high-risk showing that the models have lots of false postives.

The recall was all over the place with the first 4 models' avg/total, with values of 0.57, 0.68, 0.40, 0.54. These can be interpreted as finding between 40% and 68% of all of the positive samples. Ideally it would be closer to 1 and the models would not miss out on any good loan opportunities. Once again the Ensemble Learners performed the best, with recall scores of 0.87 and 0.90 for Random Forest and AdaBoost respectively. However, the high risk recall was 0.70 for Random Forest, compared to 0.93 for the AdaBoost.

F1 scores are weighted averages of the recall and precision, so it is no surprise that AdaBoost had the best performance with 0.94 avg/total. Close behind was Random Forest with 0.93, and in third was SMOTE with 0.81. The low-risk f1 scores were all above the avg/total, and the high-risk f1 scores were all 0.10 or lower.

Overall, the Ensemble Learners outperformed the over/under samplers, but the numbers were buoyed by the models' performances of the high-risk loans. The best F1 score for the high-risk was only 0.10, which is terrible. As such, I would recommend more research on more advanced models that do a better job of identifying the bad risk. For the time being, the AdaBoost model performs well overall, but needs some additional verification on high-risk instances. 
