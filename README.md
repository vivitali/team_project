# Team Project

### Video link

Kristina Talalaievska: https://drive.google.com/file/d/1YpJATT5cnvVBbK1cX68f8Wd4FgXgr-7P/view?usp=share_link

### Description

The project aims to analyze a dataset to predict the likelihood of developing asthma based on known factors like age, gender, ethnicity, education level and diagnosis. By using this information, we built a model to accurately forecast the risk of asthma. This predictive tool is vital for for helping in better management of the disease. Our team employed two machine learning techniques for this analysis: KNN and logistic regression.


### Methodologies used:
 1. KNN targets  to classify data points based on their proximity to other points in the dataset.
 2. Logistic Regression aiming  to predicts the probability of asthma occurrence by modeling the relationship between the dependent variable (diagnosis)  and various independent variables (age, gender, ethnicity and education level).

 Rules of Engagement:
 1. Transparent and clear communication within the team members.
 2. Collaboration and teamwork.
 3. Respect and professionalism in sharing different viewpoints and constructive feedbacks.
 4. Identifying strong expertise of each team member to effectively contribute to the project.
 5. Conducting team meetings and summarizing the key points for discussion on the common shared Google Doc.
 6. Transparency in sharing ideas openly.
 7. Supporting each other and clarifying if one of the team members has difficulties in understanding the project process.
 8. Continuous improvement in developing the model.


### Video link

Yuanyuan (Caroline) Zhang: https://drive.google.com/file/d/1w6S_ISXUlIID1eEA0uiGH29YGZLqPq5u/view?usp=drive_link

### Description

Use KNN and logistic regression to predict the asthma diagnosis based on known factors, such as demographic details and life style factors.


### Steps to analyse the dataset

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


### Interpretation of the analysis:
### Imbalanced dataset:
The model cannot predict posistve diagnosis, even thouth the accuracy is high at 95%, mostly due to the predicted result are all negative.

### Reasons:
It seesm the dataset is imbalanced where there are 124 positive diagnosis of Asthma out of the entire 2400 records.The corelations between predictor variables and target variable are not strong, there is no correlation above 0.1, while the strongest corelation is Exercise Included at 0.05, the 2nd strong correlation is with Chest Tightnesss (0.04), followed by Lung Function FVC (0.030), Wheezing (0.027), Dust Exposure (0.026), Coughing (0.024),Lun Function FEV1 (0.023), Nightime Symptoms (0.021) as well as Ethnicity_3 (0.022). (refere to below table for Correlation to related factors from the analysis)

### Solution:
I was tring to solve the imbalanced dataset by increasing the traing set from 80% to 90% (or even tried 95%). The result still does not make any imporvement on predicting positve diagnosis. Maybe there are better ways to solve the issue. But due to the time limit of this project, I will deal with it at a later time. Or maybe we can find a better dataset to work on for the next project.

### Correlations analysis

Most important factor:
Among all the predictor values, Exercise Induced variable has the strongest correlation with the diagnosis. Exercise-induced asthma is when the airways narrow or squeeze during hard physical activity. It causes shortness of breath, wheezing, coughing, and other symptoms during or after exercise. (reference: https://www.mayoclinic.org/diseases-conditions/exercise-induced-asthma/symptoms-causes/syc-20372300). This shows that exercise seems to be a contributing factor to induce Asthma.

Other related factors:
Most of the related factors are symptom related, such as Gastroesophageal Reflux, Wheezing, Chset Tightness, Couphing, Nighttime Symptoms. Some related factores are based on medical exams, such as Lung function FEV1 and Lung Function FVC.

Demographic factors:
Demographic details have lower correlations (below 0.02) to the diagnosis (Age has a 0.015 correlation, Gender has little correlation at 0.003), except that Ethnicity_3 has a stronger correlation 0.022. We need the interpretations on what the Ethnicity_3 entails, as this indicates the Ethnicity value equals 3 from the orignial dataset. Once we know what Ethnicity 3 represents, we would have a better idea about the analysis.

Education and lifestyle factors:
We also understands that the educaiton level or lifestyle factors (BMI, Physical Activity, Diet Quality, Pollution Exposure), have little correlations (below 0.02) to the diagnosis,  except that Dust Exposure has a relatively stronger correlation 0.026, Smoking has a slightly strong correlation 0.019, followed by Sleep Quality at 0.018, Pollen Exposure at 0.015.

Medical symptons and history:
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




## Video Link:
Jinrong Liu: https://vimeo.com/965691090


## Project Objective

Our project focuses on analyzing Asthma based on a dataset of Patient ID, Demographic details, lifestyle factors, environmental and allergy factors, Medical history, Clinical Measurements, Symptoms, Diagnosis information, and Confidential information. The goal of the analysis is to understand how the factors affect Asthma. Therefore, we select Diagnosis as a dependent variable, and others are regarded as independent variables. 

Before working on the project, we made our team's Rules of Engagement. The details are summarized below:
1. Everyone needs to take time to participate in the meeting and discussion;
2. Everyone is free to share ideas, questions, and improvements on Google doc;
3. Transparent and clear communication among the team members;
4. Everyone needs to make a commitment to complete the team project;
5. We are always welcoming any developments and suggestions, and everyone is responsible for these developments and improvements during the working period;
5. Everyone needs to engage each allocation and be able to fully complete all allocation works.

## Project Process

Our team wanted to know which model or models fit the dataset, so we used different models to test the dataset. For my part, I used a Multilinear regression model. The model failed as I got the negative number of R-squared. After a discussion with team members, I realized the big mistake was because the dataset was based on classification rather than numbers. Thus, I am continuing to use the model that fits for classification. I tested the three models: Random Forest, SVM(Support Vector Machine), and KNN (K-Nearest Neighbors).

### Random Forest:
I used the model of Random Forest to test how the model fits the dataset. However, I  did not achieve an excellent accuracy result. The accuracy rate of the model is 91.2317%. The overall result is good, but the model has an important disadvantage. The model is imbalancing as the F1-score is 0.95, and the supported data is 454 for class 0 (male); whereas there is only 0.09 of F1-score and the supported data is 25 for class 1 (female).

### SVM (Support Vector Machine):
After realizing the Random Forest Model's shortcomings, I decided to use an SVM (Support Vector Machine). The overall result is evenly poorer than the first model. The F1 Score of the model is 0.68, and the supported data is 681 for class 0. For class 1, the F1 Score is 0.09, and the supported data is 37. Additionally, the ROC AUC Score of the model is 0.5281. In other words, the model is still not as good as we expected.

### K-Nearest Neighbors:
Due to the limited time, I decided to try the final model- KNN, which i have leared from class. Surprisingly, the result is better than the first two models. The overall result is 94.0114%, and other factors (Mean, Standard deviation, quartiles) look good. As a result, I decided to use KNN to conduct the statistical analysis.

## Project Analysis

PatientID:
The PatientID ranges from 5034 to 7425, with a standard deviation suggesting a spread of IDs. All IDs are unique as the count matches the number of rows.

Age:
The age of participants ranges from 5 to 79 years, with a mean age of approximately 42 years. This indicates a middle-aged adult population with a significant range, covering children to elderly.

Gender:
Gender is coded as binary (0 and 1). The mean close to 0.49 suggests a near-even split between the two genders.

Ethnicity:
Encoded with values from 0 to 3, representing different ethnic groups. The maximum value of 3 and a mean of around 0.67 indicate a diversity of ethnic backgrounds, with potential skew towards specific groups.

Education Level:
Values range from 0 to 3, which might represent increasing levels of educational attainment. The data skews towards higher education levels, with a mean around 1.31.

BMI:
Body Mass Index (BMI) values range from 15.03 to 39.96, indicating a variety from underweight to obese categories. The mean BMI is about 27, which is classified as overweight.

Smoking:
This is likely a binary feature, with a mean close to 0.14 suggesting that a smaller proportion of the population are smokers.

Physical Activity:
Weekly hours spent in physical activity range from near 0 to about 10 hours, with a mean slightly over 5 hours. This might suggest moderate activity levels across the population.

Diet Quality:
Diet quality scores range from 0 to 10, with a mean of around 5.02, indicating a moderate diet quality on average.

Sleep Quality:
Sleep quality scores also range from about 4 to 10, with a higher mean of 7.09, suggesting generally good sleep quality among participants.

Gastroesophageal Reflux:
Appears to be a binary indicator (0 or 1), with a low mean (about 0.16), indicating that few participants suffer from this condition.

Lung Function (FEV1 and FVC):
Both Forced Expiratory Volume in 1 second (FEV1) and Forced Vital Capacity (FVC) show a wide range in values, suggesting variability in lung function among the participants. The means (about 2.55 for FEV1 and 3.74 for FVC) along with their standard deviations (about 0.86 for FEV1 and 1.30 for FVC) indicate diverse respiratory health statuses.


## Project Results

Demographic Diversity:
The dataset spans a wide age range from 5 to 79 years, with an average age around 42 years, indicating a diverse demographic that includes children, adults, and the elderly. The standard deviation in age suggests a broad representation across different life stages.

Gender Balance: 
Gender distribution is nearly equal with a mean very close to 0.5, implying an almost even split between the two genders represented in the dataset. This balance allows for gender-comparative analyses without major adjustments for gender disparities.

Ethnic and Educational Diversity: 
The participants come from varied ethnic backgrounds with values ranging from 0 to 3, and the dataset shows a good mix, although with a slight skew towards lower numbered ethnic groups. Education levels vary from no formal education to higher education degrees, suggesting the dataset captures a wide socioeconomic spectrum.

Health Metrics Variability:
BMI values range significantly from underweight to obese categories, with a mean indicating the average participant is at the upper edge of the normal weight range. This variability, combined with a mean physical activity of about 5 hours a week and moderate scores in diet and sleep quality, underscores the potential to explore associations between lifestyle factors and health outcomes.

Specific Health Concerns:
A small proportion of the dataset indicates issues like smoking and gastroesophageal reflux, which could be critical for targeted health interventions.

In summary, the dataset provides an adequent foundation for analyzing health and lifestyle correlations, demographic impacts on health, and the possiblity to find the best fit model in the future.


## Video link

Anna Zheng: https://drive.google.com/file/d/14VACegJThk3TINtBU4Y1W-bm6HeDQFIv/view?usp=drive_link

### Description

This project aims to analyze asthma data set and to use the dataset to train a model to predict if a patient has asthma. 


### Methodologies used:
Split the data into training set and test set to train a KNN model and to view the accuracy score. Started with checking if the gender, age, education levels are skewed by data visualizing and then fit the model. The accuracy score is pretty satisfying with KNN.
