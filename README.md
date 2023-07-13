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

## The Data
### Exploratory Data Analysis
