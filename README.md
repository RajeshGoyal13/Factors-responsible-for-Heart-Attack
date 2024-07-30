
# Business Understanding:

From a business perspective, we are tasked with identifying key drivers for heart attack.Description of Each variable ###Age | Age in years Sex | 1 = male; 0 = female cp | Chest pain type trestbps | Resting blood pressure (in mm Hg on admission to the hospital) chol | Serum cholesterol in mg/dl fbs | Fasting blood sugar > 120 mg/dl (1 = true; 0 = false) restecg | Resting electrocardiographic results thalach | Maximum heart rate achieved exang | Exercise induced angina (1 = yes; 0 = no) oldpeak | ST depression induced by exercise relative to rest slope | Slope of the peak exercise ST segment ca | Number of major vessels (0-3) colored by fluoroscopy thal | 3 = normal; 6 = fixed defect; 7 = reversible defect Target | 1 or 0

link to Jupyter Notebook: 
## Data Understanding
The first step for this assignemnt was to understand the data. Looked into the attributes of the data. Most of the columns have non- numeric data. There are any columns which have null data also.

<img width="628" alt="Screenshot 2024-07-03 at 7 44 17 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/abf3c9b4-1601-48e7-b2e8-a3bc86f8ba0b">

Checked what type of data is. Most of the data is numeric.

<img width="465" alt="Screenshot 2024-07-03 at 7 44 40 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/1e85b3c2-9d25-47f6-ac6d-f99f32792b8e">

<img width="465" alt="Screenshot 2024-07-03 at 7 45 03 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/58df79ed-0f56-49a3-a461-c7fefa8f1751">

Also checked, if there is any deuplication of data.

<img width="666" alt="Screenshot 2024-07-03 at 7 45 28 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/e0407c2f-ab86-4243-b554-8ab65556316d">

There was some data duplication, so removed the data.

## Data Preperation
After our initial exploration and fine tuning of the business understanding, it is time to construct our final dataset prior to modeling. Here, we want to make sure to handle any integrity issues and cleaning, the engineering of new features, any transformations that we believe should happen (scaling, logarithms, normalization, etc.), and general preparation for modeling with sklearn.

Created the heat map to see how the various features are interlinked

<img width="738" alt="Screenshot 2024-07-03 at 7 52 05 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/c4f227bb-ef46-4181-b9d3-5edbfb02a1be">

Heat map shows that few factors have postive / negative impact and few have minimum impact. Created various bar charts to see, how is the data structred.

<img width="991" alt="Screenshot 2024-07-03 at 7 52 48 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/a07261e6-6c9d-4ef6-a3b7-09fe57e73898">

Created varuous bar charts withrespect to Target data to see how the data is distributed.

<img width="991" alt="Screenshot 2024-07-03 at 7 53 04 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/74cfbd12-e8a1-40c6-9c29-be3f5d019346">

Based on above analysis, dropped some of the columns. Created the short data set:

<img width="847" alt="Screenshot 2024-07-03 at 7 53 25 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/524bf040-de47-40f8-9585-b895bd1ccca8">

## Modeling:
Once the data set is ready. Next step is to create models. First of all, I calculated permutation importance. It helped to understand which features/ columns are more important than others. Looking at it, it helps to drop some of the coulmns which do not have importance. Looking at the below list, it shows that Year, Odometer, 8 Cylinders, Diesel fuel, 4 cylinders are more imporant features in the price of the car.

<img width="847" alt="Screenshot 2024-07-03 at 7 57 57 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/921d4df7-c425-4b16-83aa-5590a5cde331">

Created the pipelines for three different models: Sequential Feature selector, Ridge Regression and Ordinary Least square models.

<img width="847" alt="Screenshot 2024-07-03 at 7 59 21 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/8192e454-9919-4e60-8951-8075c3923819">
<img width="603" alt="Screenshot 2024-07-03 at 7 59 47 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/4899b3f5-21cd-4bec-b756-10deb76d667d">
<img width="658" alt="Screenshot 2024-07-03 at 8 00 01 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/21f74814-2337-4f81-a795-ae3d01892f39">

Here are the co-efficients and factors found by each model:

<img width="300" alt="Screenshot 2024-07-03 at 8 04 07 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/5f900a90-19f3-476f-85a1-b5d4621e979d">
<img width="300" alt="Screenshot 2024-07-03 at 8 04 22 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/0d38d28f-cfa5-4640-ab53-c35aff400899"><img width="300" alt="Screenshot 2024-07-03 at 8 04 35 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/5ad46afa-109c-4507-9646-9c6c7881ae18">


For eaach model, Cross validation was done by using the below code:

<img width="994" alt="Screenshot 2024-07-03 at 8 05 56 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/0d6ebb93-443d-499a-9227-8651314ff9cf">

## Evaluation:

Evaluated the MSE and R2 score of each module. Here is the comparison of the three models.
<img width="409" alt="Screenshot 2024-07-03 at 8 06 57 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/fd6f17f3-6445-4160-a02b-c2e2a9fc8662">
<img width="409" alt="Screenshot 2024-07-03 at 8 07 06 AM" src="https://github.com/RajeshGoyal13/Factors-responsible-for-Heart-Attack/assets/161057282/13328245-6e01-44f4-94f9-669c748157c1">





