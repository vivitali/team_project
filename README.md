# Team Project

### Description

Use KNN and logistic regression to predict the asthma diagnosis based on known factors, such as demographic details and life style factors.

### Steps took to analyse the dataset

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



# What insights have been generated from the analysis?

### Imbalanced dataset:
The model cannot predict posistve diagnosis, even thouth the accuracy is high at 95%, mostly due to the predicted result are all negative.

### Reasons:
It seesm the dataset is imbalanced where there are 124 positive diagnosis of Asthma out of the entire 2400 records.The corelations between predictor variables and target variable are not strong, there is no correlation above 0.1, while the strongest corelation is Exercise Included at 0.05, the 2nd strong correlation is with Chest Tightnesss (0.04), followed by Lung Function FVC (0.030), Wheezing (0.027), Dust Exposure (0.026), Coughing (0.024),Lun Function FEV1 (0.023), Nightime Symptoms (0.021) as well as Ethnicity_3 (0.022). (refere to below table for Correlation to related factors from the analysis)

### Solution:
I was tring to solve the imbalanced dataset by increasing the traing set from 80% to 90% (or even tried 95%). The result still does not make any imporvement on predicting positve diagnosis. Maybe there are better ways to solve the issue. But due to the time limit of this project, I will deal with it at a later time. Or maybe we can find a better dataset to work on for the next project.

### Interpretation of the analysis:

Among all the predictor values, Exercise Induced variable has the strongest correlation with the diagnosis. Exercise-induced asthma is when the airways narrow or squeeze during hard physical activity. It causes shortness of breath, wheezing, coughing, and other symptoms during or after exercise. (reference: https://www.mayoclinic.org/diseases-conditions/exercise-induced-asthma/symptoms-causes/syc-20372300). This shows that exercise seems to be a contributing factor to induce Asthma.

Most of the related factors are symptom related, such as Gastroesophageal Reflux, Wheezing, Chset Tightness, Couphing, Nighttime Symptoms. Some related factores are based on medical exams, such as Lung function FEV1 and Lung Function FVC.

Demographic details have lower correlations (below 0.02) to the diagnosis/target variable (Age has a 0.015 correlation, Gender has little correlation at 0.003), except that Ethnicity_3 has a stronger correlation 0.022. We need the interpretations on what the Ethnicity_3 entails, as this indicates the Ethnicity value equals 3 from the orignial dataset. Once we know what Ethnicity 3 represents, we would have a better idea about the analysis.

We also understands that the educaiton level or lifestyle factors (BMI, Physical Activity, Diet Quality, Pollution Exposure), have little correlations (below 0.02) to the diagnosis,  except that Dust Exposure has a relatively stronger correlation 0.026, Smoking has a slightly strong correlation 0.019, followed by Sleep Quality at 0.018, Pollen Exposure at 0.015.

Some medical symptoms or medical history, such as Family History of Asthma, History of Allergies, Eczema, seem to have little correlation on the diagnosis, except that Hay Fever has a slightly strong correlation 0.019, followed by shortness of breath at 0.015, Pet Allergy at 0.013.


#### Correlations to related factors from the analysis:

DustExposure              0.025972
GastroesophagealReflux    0.022770
LungFunctionFEV1          0.023336
LungFunctionFVC           0.029629
Wheezing                  0.027197
ChestTightness            0.039278
Coughing                  0.024193
NighttimeSymptoms         0.021965
ExerciseInduced           0.053956
Ethnicity_3               0.022309

#### Correlations to other factors from the analysis:

Age                    0.015111
Gender                 0.003128
EducationLevel         0.008185
BMI                    0.012522
Smoking                0.019321
PhysicalActivity       0.005066
DietQuality            0.003149
SleepQuality           0.018022
PollutionExposure      0.004535
PollenExposure         0.015099
PetAllergy             0.013078
FamilyHistoryAsthma    0.001334
HistoryOfAllergies     0.001951
Eczema                 0.008592
HayFever               0.019141
ShortnessOfBreath      0.015281
Ethnicity_0            0.011398
Ethnicity_1            0.001778
Ethnicity_2            0.005584
Name: Diagnosis, dtype: float64


