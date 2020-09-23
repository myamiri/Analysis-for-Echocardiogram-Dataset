# Analysis-for-Echocardiogram-Dataset

# Problem

Predict whether a patient (has) survived at least 2 years



# Solution

I used two methods:

. Random Forest

. Logistic Regression



# Data


All the patients suffered heart attacks at some point in the past. Some are still alive and some are not. The survival and still-alive variables, when taken together, indicate whether a patient survived for at least one year following the heart attack.

. survival – the number of months patient survived (has survived, if patient is still alive). Because all the patients had their heart attacks at different times, 
  it is possible that some patients have survived less than one year but they are still alive. Check the second variable to confirm this. Such patients cannot be used for the     prediction task mentioned above.
. still-alive – a binary variable. 0=dead at end of survival period, 1 means still alive
. age-at-heart-attack – age in years when heart attack occurred
. pericardial-effusion – binary. Pericardial effusion is fluid around the heart. 0=no fluid, 1=fluid
. fractional-shortening – a measure of contracility around the heart lower numbers are increasingly abnormal
. epss – E-point septal separation, another measure of contractility. Larger numbers are increasingly abnormal.
. lvdd – left ventricular end-diastolic dimension. This is a measure of the size of the heart at end-diastole. Large hearts tend to be sick hearts.
. wall-motion-score – a measure of how the segments of the left ventricle are moving
. wall-motion-index – equals wall-motion-score divided by number of segments seen
. Mult-A derivate   variable (suggested that it can be ignored)
. Name-The Name of the patient 
. Group-Group (Has been considered meaningless and suggested to ignore)  
. alive-at-1 – Boolean-valued. Derived from the first two attributes. 0 means patient was either dead after 1 year or had been followed for less than 1 year. 1 means patient     was alive at 1 year.



# Modeling

I used Random Forest that is a bagging model to avoid overfitting which is a very common problem in case we don’t have enough samples.
Random forest trains several Decision Trees in parallel by using a random subset of samples and features with replacement and considers 
the average performance of the all Decision Trees as the final performance of the model.

Also, I used Logistic Regression which is a parametric model and compared the results with Random Forest. Because most of the features are continuous, 
Logistic Regression model perform well.




# Result


Both have a good performance as the numbers of false negatives in both are zero. But the number of false positives in Random Forest is less than Logistic 
Regression so its performance is better.

The Accuracy of train dataset and validation dataset are very close and this shows that we don’t have overfitting and based on the accuracy of Validation dataset 
I can say the accuracy of the models on unseen data is like the result for validation data.

