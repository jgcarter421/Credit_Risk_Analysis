# Credit Risk Analysis

## Overview
The purpose of this analysis was to use several different machine learning algorithms to predict the credit risk of of loan applicants utilizing Lending Club's credit card credit dataset.  This will assist in enabling Fast Lending to determine who to issue a loan to, and who is a bad credit risk.  

To do this, I used the following data analysis techniques:
* Oversampling 
* Undersampling
* Comination (Over and Under) Sampling
* Ensemble Learners

To determine the best machine learning model to use, I assessed the Balanced Accuracy Score, as well as the Precision and Recall Scores.  The Balanced Accuracy Score is the average of recall obtained on each class.  The Precision is the percentage of positive predictions that are correct.  Lastly, the Recall (also known as Sensitivity) is the percentage of actual positive results that are predicted correctly.

## Results
### Preparing the Data
For the machine learning model to work, the dataframe was split into columns that would be used to best predict (X) the outcome of the loan status(y).

<img width="1091" alt="Screen Shot 2022-07-06 at 7 04 46 AM" src="https://user-images.githubusercontent.com/99417460/177546044-97cd2cd2-f37a-4e6e-95c7-b3cc91012169.png">

### Testing the Data
#### Naive Random Oversampling
<img width="319" alt="Screen Shot 2022-07-06 at 7 06 43 AM" src="https://user-images.githubusercontent.com/99417460/177546361-a3f8c7d0-fc7c-4b6f-b2f3-b340a8aa78c4.png">
<img width="664" alt="Screen Shot 2022-07-06 at 7 07 24 AM" src="https://user-images.githubusercontent.com/99417460/177546448-afec6540-6d78-4a96-b58b-358090bdf1b5.png">

* The balanced accuracy score is approximately 65%.
* The Precision for low risk is 100% and the high risk is 1%.
* The Recall for low risk is 59% while the high risk is 72%.

#### SMOTE Overspampling
<img width="333" alt="Screen Shot 2022-07-06 at 7 15 56 AM" src="https://user-images.githubusercontent.com/99417460/177547944-fc9ef5cf-268e-46b1-ad13-d5eafc907362.png">
<img width="660" alt="Screen Shot 2022-07-06 at 7 16 14 AM" src="https://user-images.githubusercontent.com/99417460/177548014-d3a44cc0-e445-4cf6-9c3c-b0a695b77bd6.png">

* The balanced accuracy score is approximately 65%.
* The Precicsion for low risk is 100% and the high risk is 1%.
* The Recall for low risk is 59% and the high risk is 72%.

#### Undersampling
<img width="339" alt="Screen Shot 2022-07-06 at 7 19 38 AM" src="https://user-images.githubusercontent.com/99417460/177548623-b4f6fd6e-6bb0-49a0-95af-6711f851b216.png">
<img width="652" alt="Screen Shot 2022-07-06 at 7 19 59 AM" src="https://user-images.githubusercontent.com/99417460/177548691-21bb5a97-5580-4ab1-ad7d-aef6e462d5f8.png">

* The balanced accuracy score is approximately 54%.
* The Precision for low risk is 100% and the high risk is 1%.
* The Recall for low risk is 40% and the high risk 69%.

#### Combination (Over and Under) Sampling
<img width="347" alt="Screen Shot 2022-07-06 at 7 22 13 AM" src="https://user-images.githubusercontent.com/99417460/177549064-490d95a8-e688-41df-8641-a3cb7330d77f.png">
<img width="654" alt="Screen Shot 2022-07-06 at 7 22 34 AM" src="https://user-images.githubusercontent.com/99417460/177549137-49d92d5e-3696-4adc-ac09-103c6bdcb648.png">
* The balanced accuracy score is approximately 69%.
* The Precision for low risk is 100% and the high risk is 1%.
* The Recall for low risk is 61% and the high risk is 72%.

#### Balanced Random Forest Classifier
<img width="323" alt="Screen Shot 2022-07-06 at 7 25 46 AM" src="https://user-images.githubusercontent.com/99417460/177549708-8461668f-6839-4a5d-9978-e2cfdbc33b30.png">
<img width="664" alt="Screen Shot 2022-07-06 at 7 26 05 AM" src="https://user-images.githubusercontent.com/99417460/177549762-85dec25f-e607-4980-b370-3cb06f853b57.png">

* The balanced accuracy score is approximately 81%.
* The Precision for low risk is 100% and the high risk is 3%.
* The Recall for low risk is 89% and the high risk is 72%.

#### Easy Ensemble AdaBoost Classifier
<img width="323" alt="Screen Shot 2022-07-06 at 7 27 56 AM" src="https://user-images.githubusercontent.com/99417460/177550049-980de0da-55e2-41b7-a423-b97ab4370c13.png">
<img width="658" alt="Screen Shot 2022-07-06 at 7 28 12 AM" src="https://user-images.githubusercontent.com/99417460/177550096-7c0b9f7a-d7ad-46f8-b59c-d4849b9dd0e2.png">

* The balanced accuracy score is approximately 93%.
* The Precision for low risk is 100% and the high risk is 7%.
* The Recall for low risk is 94% and the high risk is 91%.

## Summary
Each of the Oversampling and Undersampling, and Combination Sampling had a balanced accuracy score below 70%.  They each had a Precision of 1% for high risk applications and 100% for low risk applications.  The Recall scores for these models had a low risk percentage below 61% and the high risk percentage of 72% or below.  

Both of the Ensemble Methods (Balanced Random Forest Classifier & AdaBoost Classifier) had better balanced accuracy scores.  The Balanced Random Forest Classifer had a balanced accuracy score of 81% while the AdaBoost Classifier had a score of 93%.  Both Ensemble models had Precisions of 100% for low risk applications, but performed better than the Under, Over, & Combo sampling methods for the high risk applications.  The Balanced Random Forest Classifier had a Precision of 3% for high risk applications and the AdaBoost Classifier had a 7% score.  The Recall was also better with the Balanced Random Forest Classifier having 89% for low risk and 72% for high risk.  The AdaBoost Classifier ahd a 94% Recall for low risk and a 91% for high risk.

Based on these results, I would recommend that the AdaBoost Classifier be used to predict the loan applications.  The AdaBoost Classifier had the highest balanced accuracy score and the highest Recall (Sensitivity) scores.  Each model had a 100% precision for low risk applications, but the AdaBoost Classifier performed the best for high risk applications with a score of 7%. 
