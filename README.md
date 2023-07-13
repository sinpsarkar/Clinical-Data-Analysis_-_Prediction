# Analysis of clinical data of patients and prediction of potentialilty of disease

![Header Image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/29dca4bf-804e-4e79-b922-f317f2b2053b)
## Background
Machine learning and artificial intelligence endeavours to infer knowledge from raw data, concerned with development of algorithms and provides actionable recommendations to help researchers and health institutes flag, predict and prevent risks associated with clinical research. Machine learning in healthcare is a growing field of research in precision medicine with many potential applications. As patient data becomes more readily available, machine learning in healthcare will become increasingly important to healthcare professionals and health systems for extracting meaning from medical information.  

There is a wide range of potential uses for machine learning technologies in healthcare. Some of these are mentioned below in brief:

- A Diagnostic tool aided with Machine Learning algorithm can be used in medical imaging like X-rays and MRI scans to look for patterns that indicate a particular disease. This could potentially help doctors make quicker, more accurate and **improved diagnoses** leading to improved patient outcomes.

- Machine learning in healthcare could be used to analyze data and medical research from clinical trials to find previously unknown side-effects of drugs. This could help in **improve patient care, drug discovery, and the safety and effectiveness of medical procedures.**

- Machine learning in healthcare could be used to develop better algorithms for managing patient records or scheduling appointments. This type of machine learning could potentially help to **reduce cost** in terms of time and resources.

- Machine Learning could help in developing systems that proactively monitor patients and provide alerts to medical devices or electronic health records when there are changes in their condition. This type of data collection machine learning could help to ensure that patients receive the right care at the right time, and hence **improved care**.

## Problem Statement (For the current Project)
We have access to the clinical data of some random patients undergoing treatment for a disease. The objective of this project is to enable prediction if a patient has the disease.

## Evaluation Metrics :
In the analysis of the available data, we observe that the classes (target) is highly imbalanced, with roughly 18% of the data resembling Class 1(Patient has disease).
Also, in this analysis and prediction, the cost of False Negative (predicting no disease for patient who actually have disease) and False Positives (predicting patient has disease for patient who actually do not have the disease) is very high and critical.
With these considerations, F1 score is a metric of choice in this case.
F1 Score is calculated as the Harmonic-Mean of Precision and Recall. It is formulated as below:

![f1 score](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/29acd334-b699-4689-aabf-98ce0a74cdbe)

## The Data : Exploratory Data Analysis

> <ins>Available datasets</ins>:

- train.csv<br>
- test.csv<br>
-------------------------------------
**NOTE:**
Due to security pertaining to medical data, the data available for analysis and building ML algorithms had the following changes/ mask:
- Patient's name and personal details omitted
- Patient's id encrypted
- Original column headers masked
- A small subset of data made available
-------------------------------------

> <ins>Data Definitions</ins>:
The dataset **train.csv** has **617 rows** **56 columns** (including target)<br>
![df_train_shape](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/a49d246a-e6ed-4cf1-9290-2cdda9870e0d)

> <ins>Continuous/ Numerical Features</ins> : 55 <br>
NA1, NA2, NA3, NA4, NA5, NA6, NA7, NA8, <br>
NB1, NB2, NB3, NB4, NB5, NB6, NB7, <br>
NC1, NC2, NC3, NC4, NC5, NC6, NC7, NC8, NC9, NC10, <br>
ND1, ND2, ND3, ND4, ND5, ND6, ND7, ND8, ND9, ND10, <br>
NE1, NE2, NE3, NE4,  NE5, NE6, NE7, <br>
NF1, NF2, NF3, NF4, NF5, NF6, NF7, NG1, <br>
NG2, NG3, NG4, NG5, NG6<br>

> <ins>Categorical/Non-Numerical Feature(s)</ins> : 1<br>
Id, CE1

> <ins>Target Variable</ins> :<br>
Class

> <ins>A Look at the data</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/c4236843-726d-4621-9c67-000508aed4d9)

> <ins>Statistical Summary of data</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/b509609a-51f8-49d2-8675-9887fc99c30e)


> <ins>Check for missing values in the data</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/aea8115a-5ebb-4bf4-83a4-4b1058c5a163)

> <ins>Different Categories and distribution for Categorical Feature</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/09a6966d-8aa6-4a1f-8b40-a3ead5d48ede)

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/c00401be-25e2-4e25-a0aa-228c76e24d00)



> <ins>Plot for the Target Variable</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/84a7d343-38f3-4137-ac4b-5a19b93d229f)

> <ins>Plots for Continuous Variables</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/d37ba9e9-9634-40b6-94f0-108c8dc911fa)

> <ins>TSNE Plot to check for clusters</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/fdd157d9-0d7e-4921-afb5-09ed6e0d4543)

> <ins>Correlation among different features</ins>

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/44d40513-9872-47a3-81ea-4d5dad93c8ff)


## **Observations from the EDA**:
- Some features have null/missing values
- We observe Right Skewness in almost all the features
- The Categorical Feature **CE1** only has 2 categories - **A** and **B**
- Spike observed at beginning for feature - **NA8**<br>
- Different spikes for Class 0 & 1 observed for feature - **NB3**<br>
- Uniform distribution observed for Class 0 only (not Class 1) for feature - **NB5**<br>
- Multiple peaks observed in the distributions for the features : **NC10**, **NE5**, **NG6**<br>
- After detailed analysis (and transformations), we found that the unobvious multiple - peaks or peaks at beginning / end was because of trimming of the data.
- The TSNE highlights presence of some clusters, however, the data points can't be easily separated/ identified into one-or-the-other class
- We also observe some very high correlation among some of the features. We may check the impact of having/not having these features while evaluating the models.


## Approach & Challenges
With all the observations made from the EDA, the obvious steps would be
- Handling the missing values.
- Imputing / Dropping outliers
- Removing either of the features with high correlation
- Train and evaluate models
- Make predictions on the test data

**However the challenge here is** -  these steps are easier said than done for the current scenario, given that the size of the dataset is very limited (617 records). Removal / imputation of/for any record may introduce new biases. 
However, we are in luck this time around to observe very few outliers, which <i> we can drop</i>.<br>
For the minimum and maximum trimming of the data, we shall ignore the features NB5,NC7,NC10,NA7,NB1,NA8,NB3,NE5,NG6 and check if it helps in improving the performance of the model. If not, we shall let these be there in the model.
From the observations made during the EDA, a linear model may not be very suitable for this classification problem. However, we shall still evaluate various models, including some linear models as well.

**The challenge** - Before we dive in to tackle the challenge, let us first understand - **what is the challenge?**.
- We have access to a very limited data
- We can't afford to come up with an ML model with very bad performance, as a bad prediction may cost heavily in terms of life and resources
- We can't drop records (due to outlier or anything else) or impute these from the limited records we have as this may in turn introduce some new biases, and it eventually result in more loss of data.

**Approach / Solution** 
- We carry on with the data-preprocessing steps minus outlier treatment (and treatment of max-min trimming).<br>
- We still do the train-test split of the data.<br>
- Because of small train dataset, the training time of a model will be very small. We use this to our advantage and evaluate many base models.
- Evaluate the performance of the base models using K-Fold cross-validation on the train split of the dataset.<br>
- Pick the model(s) with best performance.<br>
- Do the Hypermeter tuning for these selected models.<br>
- Train these models on the train split of the datset.<br>
- Do the predictions on test dataset. We can use the Confusion Matrix here to decide on to the final model.

## Data Pre-processing

To prepare the data for the models, we do the following pre-processing:

**NOTE** - To avoid leaking of information to the test split, we do the train-test split before applying any other method to the data. However, we shall need to do encoding of categorical variables for the test split as well.

 - **Train-Test Split** - Using test-size = 25%.


- **Null Value Treatment** - Impute the missing values with the feature median. We also used KnnImputer and feature mean to impute the missing values, however, the models seemed to give better score for imputation done with feature median.

- **Transformation** - in EDA, we observed that for some of the features the data was skewed, or the data was concentrated over a very small range of values. We tried log transformation and square transformation for these features and used these new features during the evaluation. However, we didn't observe a significant improvement in the scores of the models. Hence, we discarded the changes.

- **Encoding Categorical Variables** - for the categorical feature **CE1**. As the feature only has 2 unique values, so we used **LabelEncoder**. Though the best choice would have been **one-hot encoding** to avoid accidental introduction of <i>ordinality</i>, which LabelEncoder may introduce. But let us evaluate the models with LabelEncoder for now.

- **Standardization** - StandardScaler used to standardize all the features to a common scale.

## The Model

Our base models to evaluate on:
- LogisticRegression
- KNeighborsClassifier
- SVC
- DecisionTreeClassifier
- RandomForestClassifier
- LGBMClassifier
- VotingClassifier
- XGBClassifier
- GaussianNB
- BaggingClassifier


We used **RepeatedStratifiedKFold(n_splits=5, n_repeats=5)** to evaluate the base models on using the **f1** scoring. Below are the results:

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/0fecc330-e8df-4af0-bc8c-574dc6b65c41)


As we observe from the evaluation, **Light GBM** and **XGBoost** perform the best withough hyperparameter tuning.<br>
We used **RandomizedSearchCV** for the hyperparameter tuning of these models using **f1** scoring.<br>
We used the best hyper-parameters obtained in the last step to train on train split of the data.<br>
Below are the confusion matrix we got on applying these models on the tes split of the data.

![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/019f9344-b78e-4cd6-b834-b96e147732ba)

## Conclusion

We were able to achieve and **f1 Score** of **0.8** approximately for both the models **XGBoost** and **Light GBM**. And as the confusion matrix shows, both the models show similar results. We can use either of them for predictions.

This was a very exciting project. We were able to help in providing a solution for predicting the potentiality of a disease in a patient.


![image](https://github.com/sinpsarkar/Clinical-Data-Analysis_-_Prediction/assets/45538409/b6397b4b-2dfe-4698-8b60-8fc7f561a353)

