# Disease-Prediction-using-EMR
### Overview:
The aim of the project is to provide data driven solution using machine learning methodologies for the electronically generated medical records. The dataset is
downloaded from EMRBOTS.ORG which generates artificial medical records concerning patients privacy. 
<p> Using provided dataset, this project predicts patients' generic disease, age and lab test type. The dataset contains information on the patients' 
demographics, vital signs, lab tests, and diagnoses.

### About Dataset:
The EMR dataset consists of a total of 10,000 records with 21 features including patient ID, age, gender, race, vital signs, lab tests, and diagnoses. 
The dataset is artificially generated to protect the privacy of the patients. The dataset is uploaded in this repository under Data folder. EMRBOTS.ORG allows you 
to download data of different size.

### Data Preparation and Feature Engineering:
The four tables are merged on 'patientID' to prepare the dataset for training and testing purpose. The data preprocessing steps included handling missing 
values, data normalization, and data encoding. The dataset contains patients Date of Birth. Patient's age is calculated using datetime function considering current 
date. Dataset contained categorical data which is tranformed into binary using One Hot Encoding method. Accuracy of the predicted results are 97%.
<p> Lab Test type is treated as a target variable to determine the most common type of lab test required for the patien's. This can help medical institute the predict 
the number of lab tests to be carried out in next few days so that they can optimize the pre-ordering and re-stocking of the necessary elements.
<p> The most challengeing task for us is to predict disease as there is no single relevant attribute in our dataset which contains information about the disease patient
is cured with. To overcome this, approximately 30 most common ICD codes were computed and the generic disease which requires those ICD codes in treatment is manually 
entered in the dataset (list is created and matcher function is applied to map it with the ICD codes). However, the new dataset we obtained was highly biased. You can see
the distribution in below screenshot. 
<br> ![image](https://user-images.githubusercontent.com/68314057/235053702-f4b5f682-5850-4ccf-8148-3909287e14c5.png) </br>
<p> Features are selected using correlation matrix for further prediction of patient disease. 

### Modeling:
The train to test data ratio is 80 and 20% respectively. Machine learning models used for the predictions are regression, KNN, Random Forest, SVC and XGBoost. The 
best performing model is XGBoost. however, all the predicted results were highly biased becaused the biased training data. We used accuracy, precision, recall, and 
F1-score as the evaluation metrics for our models

### Future Work:
For better accuracy, the bias in the new dataset created after mapping the disease should be reduced. A better and more efficient approach to be determined for
mapping the specific disease with the ICD codes and then try to make the disease prediction of the patients. Look at the additional resources collected during and after
project deadline for improving accuracy and model performance.

### Instruction:
This project was a part of UMBC graduate Data Science program's Introduction to Machine Learning and Data Science subject's curriculum. 
