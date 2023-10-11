# Chronic Heart Disease Prediction

According to the Centers for Disease Control and Prevention, “One person dies every 34 seconds in the United States from cardiovascular disease”

One major challenge is the detecting of the disease. There are tools that can forecast heart disease, but they are either expensive or ineffective in calculating the likelihood of heart disease in a human. Since there is a lot of data available nowadays, we can use data mining methods to search for hidden patterns. In medical data, the hidden patterns might be exploited for health diagnosis.

## Data
We used the  Behavioral Risk Factor Surveillance System (BRFSS) dataset (Data download: https://www.cdc.gov/brfss/annual_data/2021/files/LLCP2021XPT.zip). 

This dataset is the most comprehensive collection of state information on U.S. citizens' risk behaviors, chronic health issues, and utilization of preventive care in the country. The District of Columbia, three U.S. territories, and all 50 states are currently included in the data collection areas of BRFSS. The BRFSS is the biggest continually running health survey system in the world, conducting over 400,000 adult interviews each year.


## Preprocessing
Data preprocessing is a phase in the data mining and data analysis process that converts raw data into a format that computers and machine learning algorithms can understand and evaluate.
These are the following pre-processing methods we have applied to our dataset:

- Null Values/Missing Values: This part included identifying incomplete, inaccurate, duplicated or null values in the data. These values were then deleted as removing a few missing record wouldn’t impact the distribution of your dataset. 
- Encoding: We used one-hot encoding for converting the data to prepare it for an algorithm and get a better prediction.
- Noisy data: Noisy data is useless information that computers are unable to understand. For this dataset, we removed values which were refused/don’t know/not asked to the person.

## Data Visualization
The graphic display of information and data is known as data visualization. The graphs below provide information about the dataset and how it compares to heart diseases.We have taken the following factors into account:
- Gender
- Age
- Mental Health
- Smoking Habits
- BMI

<img width="320" alt="image" src="https://media.github.iu.edu/user/21412/files/7bc92928-400d-4245-9dd6-a0c3a947c2cd">

Figure 1: Age vs Heart Diseases Graph

<img width="324" alt="image" src="https://media.github.iu.edu/user/21412/files/d187ff7f-d902-4b7d-ba93-4df1802d251e">
Figure 2: BMI vs Heart Diseases Graph


By analysing the data for these variables, it is evident that the highest percentage of people suffering from heart diseases are the people belonging to ‘>=65’ age group and ‘Overweight’ BMI which accounts for 26.5%

<img width="387" alt="image" src="https://media.github.iu.edu/user/21412/files/173d5c15-cb66-4e73-8674-43e14c5939f5">
Figure 3: High Blood Pressure vs Heart Diseases Graph

<img width="374" alt="image" src="https://media.github.iu.edu/user/21412/files/e037ccd3-2129-497c-88a2-d89e39b1b9b6">
Figure 4: High Cholesterol vs Heart Diseases Graph


By analysing the data for these variables, we observe that 12.6% of people having heart disease are found to have normal cholesterol level and no high blood pressure.

## Classification

Sampling: To find patterns and trends in the bigger data set being reviewed, data sampling is a statistical analysis approach that is used to choose, modify, and analyze a representative selection of data points.For this project, we performed oversampling using ADASYN. 

Models used: 
- Logistic Regression 
- Naive Bayes 
- Decision Tree
- Bagging Classifier
- AdaBoost Classifier
- KNN
- Neural Network

## Comparision between models

For choosing the best model, a performance evaluation metric has to be used. For this specific implementation, accuracy was used.

<p align="center">
	<img alt="Figure 7" src="https://media.github.iu.edu/user/21584/files/611e47ea-650b-4ef3-99be-ddabcdf848a8">
</p>

<p align="center">
	Figure 7: Code to demonstrate classification_report
</p>


Figure 7 is the snippet from the code that shows classification report imported from scikit learn. It outputs the data about various evaluation metrics along with accuracy, the one we are particularly interested in. y_test and ypred represent y values of testset and predicted y values by the model respectively.

<p align="center">
<img alt="Figure 8" src="https://media.github.iu.edu/user/21584/files/d539986c-fa3b-4da4-b6f2-1d59b80d162f">
</p>
<p align="center">
Figure 8: Output for the decision tree’s classification report 
</p>


Figure 8 shows accuracy among other metrics to be as 0.79 i.e. 79% accuracy for Decision Tree classifier.
In order to understand more about the performance of the specific classifier, confusion matrix and ROC curve were also extracted.


<p float="left">
  <img src="https://media.github.iu.edu/user/21584/files/285ccf1f-40d7-4c2f-89b4-cb4a860f1a53" width = 400 height = 300>
  <img src="https://media.github.iu.edu/user/21584/files/7210bfa2-5e99-400b-bd34-b73edac2a001"width = 400 height = 300> 
</p>


<p align="center">
Figure 9a (left) and Figure 9b (right) shows Confusion Matrix and ROC curve for Decision Tree Classifier respectively 
</p>


<p align="center">
<img src="https://media.github.iu.edu/user/21584/files/5161914c-568f-4770-8e79-2ee6f42b8ec2">
</p>


<p align="center">
Figure 10: Comparison of various classification models
</p>


Among all the models used for analysis as shown in Figure 10, Decision Tree classifier had the highest  accuracy of 79% and hence was the obvious choice. 

## Conclusion
Although we proceeded with the Decision Tree Classifier, the other models were not far off in terms of accuracy. The major problem encountered in terms of prediction is the highly class unbalance of the data. Using oversampling, that problem is effectively addressed improving the implementation of the models.

With the help of the finalised model, given the values related to a person i.e. values that correspond to the features considered, it is possible to predict whether the person could potentially be affected by a chronic heart disease or not. This can be further used in understanding more about the risk of the heart disease in a larger sample setting helping decision makes efficiency.

Further more experimentation in terms of hyper parameter tuning can increase the model accuracy and performance. In addition, using the BRFSS data from previous years by figuring out a decent strategy on how to approach the different number of features collected for each year can uncover useful insights and inturn improve the current approach. The true potential of this prediction can be truely discovered if combined with other forms of heart disease prediction approaches.
