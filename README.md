
# Business Understanding:

From a business perspective, we are tasked with identifying key drivers for heart attack.Heart disease, also referred as cardiovascular diseases, is broad term used for diseases and conditions affecting the heart and circulatory system. It is a major cause of disability all around the world. Since heart is amongst the most vital organs of the body, its diseases affect other organs and part of the body as well. There are several different types and forms of heart diseases. The most common ones cause narrowing or blockage of the coronary arteries, malfunctioning in the valves of the heart, enlargement in the size of heart and several others leading to heart failure and heart attack

link to Jupyter Notebook: (https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/blob/main/prompt_II.ipynb)
# Data Dictionary 
age: age in years

sex: sex
1 = male
0 = female

cp: chest pain type
Value 0: typical angina
Value 1: atypical angina
Value 2: non-anginal pain
Value 3: asymptomatic

trestbps: resting blood pressure (in mm Hg on admission to the hospital)

chol: serum cholestoral in mg/dl

fbs: (fasting blood sugar > 120 mg/dl)
1 = true;
0 = false

restecg: resting electrocardiographic results
Value 0: normal
Value 1: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
Value 2: showing probable or definite left ventricular hypertrophy by Estes' criteria

thalach: maximum heart rate achieved

exang: exercise induced angina
1 = yes
0 = no

oldpeak = ST depression induced by exercise relative to rest

slope: the slope of the peak exercise ST segment
Value 0: upsloping
Value 1: flat
Value 2: downsloping

ca: number of major vessels (0-3) colored by flourosopy

thal:
0 = error (in the original dataset 0 maps to NaN's)
1 = fixed defect
2 = normal
3 = reversable defect

target (the lable):
0 = no disease,
1 = disease

## Data Understanding
The first step for this assignemnt was to understand the data. Looked into the attributes of the data. Most of the columns have non- numeric data. There are any columns which have null data also.

<img width="628" alt="Screenshot 2024-07-03 at 7 44 17 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/abf3c9b4-1601-48e7-b2e8-a3bc86f8ba0b">

Checked what type of data is. Most of the data is numeric.Also checked, if there is any deuplication of data.
There was some data duplication, so removed the data.

## Data Preperation
After our initial exploration and fine tuning of the business understanding, it is time to construct our final dataset prior to modeling. Here, we want to make sure to handle any integrity issues and cleaning, the engineering of new features, any transformations that we believe should happen (scaling, logarithms, normalization, etc.), and general preparation for modeling with sklearn.

Created the heat map to see how the various features are interlinked

<img width="738" alt="Screenshot 2024-07-03 at 7 52 05 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/c4f227bb-ef46-4181-b9d3-5edbfb02a1be">

Heat map shows that few factors have postive / negative impact and few have minimum impact. Created various bar charts to see, how is the data structred.

<img width="991" alt="Screenshot 2024-07-03 at 7 52 48 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/a07261e6-6c9d-4ef6-a3b7-09fe57e73898">

Created varuous bar charts withrespect to Target data to see how the data is distributed.

<img width="991" alt="Screenshot 2024-07-03 at 7 53 04 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/74cfbd12-e8a1-40c6-9c29-be3f5d019346">

## Statistical summary of the features

Chest Pain:
More than 75% of the patients experience either typical angina or non-angina chest pain.
Patients who experienced atypical angina or non-angina chest pain are more likely to have a heart disease.

Resting Electrocardiogram:
Patients with Left ventricular hypertrophy are the fewest (~1.4%). The rest is almost a 50-50 split between patients with ST-T abnormality and those with normal REC tests.
ST-T abnormality seem to have a better correlation with the target, i.e the majority of patients with this kind of REC test ended up with a heart disease.

ST-Slope:
Most patients have a downsloping or flat ST-Slope of their REC test.
downsloping ST-Slopes are a strong indication that a patient might have a heart disease.

Thalassemia:
Most patients have a normal or reversable defect
Patients who have thalassemia defects (reversable + fixed) are less likely to have a heart disease. Whereas, those with normal thalassemia are more likely to have a heart condition. Sounds not intuitive.

Fasting blood sugar
Patients with lower (less than 120mg/ml) fasting blood sugar are the majority in our dataset consisting of ~85% of the sample.
Having lower resting blood sugar tends to increase the chances (~54%) of a heart disease.

Exercise Induced Angina
Two-third of the patients showed no exercise induced angina.
76% of the patients with exercise induced angina had no heart conditions. Whereas ~69% of the patients who did not experience exercise induced angina were diagnosed with heart condition.

Sex
More patients in the sample data are male.
Females seem to suffer from heart condition more than males.## Modeling:

Once the data set is ready. Next step is to create models. First of all, I calculated permutation importance. It helped to understand which features/ columns are more important than others. Looking at it, it helps to drop some of the coulmns which do not have importance.






