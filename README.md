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

##Data Set
The Patient Data is from 1999-2008 from various U.S. Hospitals in Cerner Corporation, Kansas City . The data is available in the folder marked Data and also at the UCI Machine Learning Repository.
The criteria for Data Extraction included:
- Inpatient encounter
- A “diabetic” encounter
- Length of stay 1 - 14 days
- Lab tests performed 
- Medications administered 

The dataset after cleaning has a total of  57,251 observations and 13 features. The features have been selected based on their Information Gain and Chi-Square Gain
![alt text](https://github.com/bhavikajalli/DataAnalysis-Predicting-30-Day-Readmission/blob/master/Images/IG.png)






