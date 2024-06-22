# Team Project

### Description


## Project Descriptino:
Use KNN and logistic regression to predict the asthma diagnosis based on known factors, such as demographic details and life style factors.

### Steps

1. load the dataset
   
2. observe and describe the dataset

3. preprocess data
1> drop unnecessary columns
2> analyze and convert categorical value
how do we process both numerical and categorical predictor values at the same time?
when do we neeed to standardize the predictor values?
most categorical value is coded as binary 0 or 1. two values are assigned integer 0 to 3, 'ethnicity' is not ordinal, 'education level' is ordinal.
- need to convert 4 'ethnicity' values to 4 binary columns
- education level: 4 values are ordinal, they can stay
- other binary data can stay as 0 and 1


4. split datasets into separate training and testing datasets

5. standardize the data/ feature scaling

6. fit knn model, using k = square root of n in testing dataset

7. check the prediction accuracy, use confusion matrix/table

### lession learned:

1. How to convert preprocess categorical values regarding data cleaning/preprocess
how to deal with categorical and ordinal values, 
how to convert categorical and non-ordinal variable to binary values, using one hot encoding
I have searched the methods of fixing these issues and included them as tips in this document

2. How to analyze correlcations between each predictor values and the target value
Use heatmap we can have a better idea of the most related predictor variables, which facilitates the feature selection process
From the reference link (https://medium.com/analytics-vidhya/machine-learning-2-correlation-matrix-feature-selection-class-imbalance-decision-trees-9a447fdb825), I have learned the way to analyze the correlations for each predictable factors.

3. How to deal with imbalanced dataset
After inital analysis, I found that the model cannot predict any positive cases, even though the accuracy rate is pretty high at 95%, as a result of all results are predicted as negative.
The dataset is imperfect to start with. The correlations are not strong, all are below 0.1, most of them are at 0.02 or even lower. There are only 124 positive cases out of the 2400 total records.
As suggested from the reference link from above, I tried the method of increasint the traning dataset from 80% to 90% or even 95%, but still it has little improvement on the diagnosis result. This leaves room for me to explore more solutions later on. I also understand that not all datasets are perfect.

4. Communication and engagement with other team members
Google doc: I created a team project doc on google drive to take notes from our meetings and list the things to do for each member, so that even some members might miss the meeting, all of us can still have a written document to be inline with each other. The document serves as a tracking tool to record the progress of our project and each member's input.
Slack: we also use slack to communicate after hours for any updates that we made on github.

5. Tried different to solve the issue
I have used KNN and logistic regression to analyze the dataset, both were using 90% for training set ,10% for testing. The classification report from both analysis is the same.
In this case, changing the method to analyze the dataset, does not really change the performance of the analysis.

          precision    recall  f1-score   support

           0       0.95      1.00      0.98       229
           1       0.00      0.00      0.00        11

    accuracy                           0.95       240
   macro avg       0.48      0.50      0.49       240
weighted avg       0.91      0.95      0.93       240


### video link



