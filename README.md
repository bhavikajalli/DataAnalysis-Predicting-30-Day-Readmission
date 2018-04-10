# DataAnalysis-R-30DayReadmittance

The aim of the classifier is to predict the 30-day Hospital Readmission of Diabetic Patients. This is a very interesting question as it affects many stakeholders including 
- Physicians (for managed care and healthier patients)
- Patients themselves for better quality of care and disease management
- Insurance companies for reduced costs
- Policy Makers as they can create incentive-based policy for better overall care

A successful model will
- Identify patients who may need support / monitoring after being discharged
- May reduce 30-day readmission rate
- Outpatient interventions for high-risk patients may save resources and may result in better outcomes

## Data Set
The Patient Data is from 1999-2008 from various U.S. Hospitals in Cerner Corporation, Kansas City . The data is available in the folder marked Data and also at the UCI Machine Learning Repository.
The criteria for Data Extraction included:
- Inpatient encounter
- A “diabetic” encounter
- Length of stay 1 - 14 days
- Lab tests performed 
- Medications administered 

Information source:
Impact of HbA1c Measurement on Hospital Readmission Rates: Analysis of 70,000 Clinical Database Patient Records
https://www.hindawi.com/journals/bmri/2014/781670/


#### Features
The dataset after cleaning has a total of  57,251 observations and 13 features. The features have been selected based on their Information Gain and Chi-Square Gain
<a href="url"><img src="https://github.com/bhavikajalli/DataAnalysis-Predicting-30-Day-Readmission/blob/master/Images/distribution.png" align="center" width="640" ></a>

<a href="url"><img src="https://github.com/bhavikajalli/DataAnalysis-Predicting-30-Day-Readmission/blob/master/Images/IG.png" align="center" width="640" ></a>


The final features selected are HbA1C, Age, Race, Gender, Admin Type, Length Stay, Number of Medications, Diagnosis, Number of Inpatient Encounters, Number of Emergency Visits, Number of Lab Tests, Number of Outpatient and Diabetes Medication

#### Missing Values
The dataset has minimal missing values. Admission Type had missing values and were removed because there was no way to predict these values. Race, diag_2 and diag_3 had a few (2%) missing values. These missing values were also deleted.

<a href="url"><img src="https://github.com/bhavikajalli/DataAnalysis-Predicting-30-Day-Readmission/blob/master/Images/MissingValues.png" align="center" width="640" ></a>

#### Correlation Between the features
The Correlation between the features was plotted as following

<a href="url"><img src="https://github.com/bhavikajalli/DataAnalysis-Predicting-30-Day-Readmission/blob/master/Images/corr.png" align="center" width="640" ></a>

The features are independent of each other and can be used to predict the 30 Day readmittance rate.

#### The Random Forrest Model
I first tried a Random Forest model form the mlr library. After performing Hyper parameter tuning with Random Search. The highest AUC was achieved at Ntree = 448; mtry = 4;  nodeSize = 12.

**The AUC was 0.678.** 

<a href="url"><img src="https://github.com/bhavikajalli/DataAnalysis-Predicting-30-Day-Readmission/blob/master/Images/auc.png" align="center" width="640" ></a>

#### XgBoost Model
I next tried the XgBoost model. Instead of assigning different weights to the classifiers after every iteration, this method fits the new model to new residuals of the previous prediction and then minimizes the loss when adding the latest prediction.
It is fast, memory efficient and of high accuracy.
After performing Hyper parameter tuning with Random Search. The highest AUC was achieved at max_depth = 6 and eta = 0.01.

**The AUC was 0.689.** 

#### Performance Analysis
The model's performance is poor and ready for deployment. This could be because of 

- Unbalanced dataset
- HbA1C test which is an important indicator has been performed infrequently

I have then balanced the dataset and performed Random Forest again on the dataset. The final AUC was 0.684.

The next step would be to use a neural network. 










