# credit-risk-classification

credit-risk-classification



## Overview of the Analysis



Using the dataset provided by the lending company, I created a Logistic Regression Model that generated an accuracy score of 95%. Although 
the model generated a high-accuracy, the models recall value (0.91) for non-healthy loans is lower than the recall value (0.99) for 
healthy loans. This indicates that the model will predict loan status's as healthy better than being able to predict loan status's as 
non-healthy. This is due to the dataset being imbalanced, meaning that most of the data belongs to one class label (in this case healthy 
loans greatly outweighed non-healthy loans).

![image](https://user-images.githubusercontent.com/116037923/227344482-c6e7839d-5360-4571-9d1b-53383d167daa.png)


According to the confusion matrix in step 3 [Create a LRM w/ Original Imbalanced Data]:

Out of the 18,765 loan status's that are healthy (low-risk), the model predicted 18,663 as healthy correctly and 102 as healthy incorrectly.

Out of the 619 loan status's that are non-healthy (high-risk), the model predicted 563 as non-healthy correctly and 56 as non-healthy incorrectly.

![image](https://user-images.githubusercontent.com/116037923/227347110-86a42c97-c317-441c-b2ee-24ef05bd1cdd.png)


To generate a higher accuracy score and have the model catch more mistakes when classifying non-healthy loans, we can oversample the data using the RandomOverSampler module from the imbalanced-learn library, which adds more copies of the minority class (non-healthy loans) to obtain a balanced dataset.

![image](https://user-images.githubusercontent.com/116037923/227348767-cf934919-9056-4af9-9009-ecb0c544bf16.png)




Using the dataset provided by the lending company, I created a Logistic Regression Model fit with the oversampled data that generated an accuracy score of 99%, which turns out to be higher than the model fitted with imbalanced data. The oversampled model performs better due to the dataset being balanced. The models non-healthy loans recall value increased from 0.91 to 0.99 indicating that the model does an exceptional job in catching mistakes such as labeling non-healthy (high-risk) loans as healthy (low-risk).
According to the confusion matrix in step 3 [Create a LRM w/ Resampled(oversampled) Data]:

Out of the 18,765 loan status's that are healthy, the model predicted 18,649 as healthy correctly and 116 as healthy incorrectly.

Out of the 619 loan status's that are non-healthy (high-risk), the model predicted 615 as non-healthy correctly and 4 as non-healthy incorrectly.

![image](https://user-images.githubusercontent.com/116037923/227355235-b911626b-5f0c-4b74-95d2-a29415a5ecbe.png)




## Results


Logistic Regression Model with the Original Data:

The model generated an accuracy score of 95%

![image](https://user-images.githubusercontent.com/116037923/227366724-1b2d89e4-5423-4d71-a9b7-1d5979d88997.png)


The Logistic Regression model fitted with the Imbalanced DataSet predicted healthy loans 100% of the time and predicted non-healthy loans 85% of the time.
According to the models recall scores, the model made 1% of mistakes when predicting healthy loans and made 9% of mistakes when predicted non-healthy loans.

![image](https://user-images.githubusercontent.com/116037923/227365612-9d29a79e-e912-4d9c-aa73-f1a6ba72011c.png)



Predict a Logistic Regression Model with Resampled Training Data:

The model generated an accuracy score of 99% due to the dataset being balanced.

![image](https://user-images.githubusercontent.com/116037923/227373271-c6eb1d05-07b6-4bbd-9487-b86c5b559ebf.png)


The Logistic Regression model fitted with the OverSampled DataSet predicted healthy loans 100% of the time and predicted non-healthy loans 84% of the time.
According to the models recall scores, the model made 1% of mistakes when predicting healthy loans and made 1% of mistakes when predicted non-healthy loans.

![image](https://user-images.githubusercontent.com/116037923/227374621-fa93faa9-b569-4643-bd28-e60b24bddf56.png)




## Summary


healthy loans being identified as a non-healthy loan might be more costly for a lending company since it might cause the loss of customers.
non-healthy loans being identified as a healthy loan might also be more costly for a lending company due to the loss of funds being provided by the lender.

Model fitted with the Original Data:

56 (FALSE POSITIVES) --> The actual value is healthy and the predicted value is non-healthy

102 (FALSE NEGATIVES) --> The actual value is non-healthy and the predicted value is healthy


Model fitted with Resampled Training Data:

4 (FALSE POSITIVES) --> The actual value is healthy and the predicted value is non-healthy

116 (FALSE NEGATIVES) --> The actual value is non-healthy and the predicted value is healthy
