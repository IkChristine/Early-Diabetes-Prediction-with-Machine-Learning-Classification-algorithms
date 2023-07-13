# Early Diabetes Prediction based on patients' symptoms 
Logistic Regression, Decision Tree, &amp; Random Forest


#### This project aims to train Machine Learning classification models to predict whether a patient  is at risk of developing diabetes. 
#### Key indicators (symptoms) correlated to diabetes will be identified.
#### This project will be useful to clinicians, as it will help them understand how to better avoid missing the False Positive cases who may go undiagnosed.

Data Souce: Collected data from UCI repository

<p>&nbsp;</p>

### Questions  to answer:

#### 1. Is obesity related to diabetes status? or is it independent
       <p>Chi2ContingencyResult(statistic=2.3274739583333344, pvalue=0.12710799319896815, dof=1, expected_freq=array([[166.15384615,  33.84615385],
               [265.84615385,  54.15384615]]))<p>

* The P-Value of 0.127 shows there is no significant evidence that there is a relationship between obsesity status and diabetes. 
* The expected freq array shows the values if everything was independent. Any deviation from the independent cross tab will be deemed dependent. 
* Therefore array shown is similar to the chi2 cross tab numbers, and can say that obsesity and class are independent.

<p>&nbsp;</p>
<p></p>

#### 2. Is gender related to diabetes status?

       Chi2ContingencyResult(statistic=103.03685927972558, pvalue=3.289703730553317e-24, dof=1, expected_freq=array([[126.15384615,  73.84615385],
       [201.84615385, 118.15384615]]))

* The p-value is 3.29e-24, meaning that there is significant evidence that there is a relationship between a postitive diabetes status and gender. 
* The Independent array values are significantly differnt from the cross tab values therefore shows that obsesity status and gender are dependednt (there is a relationship)
* There is significantly more females with diabetes compared to those without diabestes. (173)
* There is significantly more males with out diabetes (181) than those with diabetes.

<p>&nbsp;</p>
<p></p>

#### 3. Is polyuria related to obesity status?

       Chi2ContingencyResult(statistic=227.86583895496773, pvalue=1.7409117803442155e-51, dof=1, expected_freq=array([[100.76923077,  99.23076923],
       [161.23076923, 158.76923077]]))

* The P-Value of 1.74e-51 shows that there is strong significant evidence that there is a relationship between Polyuria status and diabetes.

<p>&nbsp;</p>

#### 4. Is gender related to polyuria status?
              Chi2ContingencyResult(statistic=36.49184228561174, pvalue=1.5330652930649977e-09, dof=1, expected_freq=array([[165.26153846,  96.73846154],
              [162.73846154,  95.26153846]]))

* P-Value of 1.53e-09 means that there is a strong evidence that there is a relationship between being a female and having a positive polyuria status.
       
<p>&nbsp;</p>

  #### 5.  Is there a relationship between age and diabetic status?
![image](https://github.com/IkChristine/Early-Diabetes-Prediction-with-Machine-Learning-Classification-algorithms/assets/104997783/b8758ca0-51c2-4fc4-b3e1-a5cb10eb3938)


* Box plots don't seem to show a big difference between the means and medians of patients with and without diabetes, as there is a lot of overlap.


<p>&nbsp;</p>

#### Correlation heatmap

![image](https://github.com/IkChristine/Early-Diabetes-Prediction-with-Machine-Learning-Classification-algorithms/assets/104997783/89ba799f-a9ab-4c37-a2fa-e10daa549700)

For gender, if negative, it is female, if positive, male
1. Diabetes is positively correlated (0.449) with females, therefore females are 44.9% more likely to have diabetes than males.
2. Patients with polyuria are 66.6% more likely to have diabetes than those who do not have polyuria.
3. Patients with polydipsia are 64.9% more likely to have diabetes than  those who do not have polydipsia.
4. Patients who have sudden weightloss are 43.7% more likely to have diabetes.
5. Patients with partial paresis are 43.2% more likely to have diabetes.
6. Female patients are 32.8% less likely to have alopecia than male patients.

<p>&nbsp;</p>

#### Top 5 important features to look up for obsesity based on the decision tree model are: 
1. Polydipsia
2. gender (Female)
3. Polyuria
4. age
5. alopecia


feature	importance
3	polydipsia	0.424208
1	isfemale	0.131796
2	polyuria	0.115480
14	alopecia	0.074900
0	age	0.066944
9	itching	0.049823
11	delayed healing	0.042698
6	polyphagia	0.033854
10	irritability	0.022087
7	genital thrush	0.016927
13	muscle stiffness	0.010640
8	visual blurring	0.006771
12	partial paresis	0.001938
4	sudden weight loss	0.001935
5	weakness	0.000000
15	obesity	0.000000

<p>&nbsp;</p>

### DummyClassifier model to establish a baseline

![image](https://github.com/IkChristine/Early-Diabetes-Prediction-with-Machine-Learning-Classification-algorithms/assets/104997783/099f29bb-92d4-4e9e-ac8a-42380b3484e0)

* 26 False positive patients - patients do not have diabetes but are predicted to have - An issue because they would have to go through additional tests and anxiety.
* 24 False negative patients - patients have diabetes but were predicted not to have it- An issue because the disease is left undiagnozed and dangerous for patient's health.
* Accuracy of the Dummy classification model is  is 52%, which is not high enough and therefore can try more models.
  

<p>&nbsp;</p>

### Logistic regression model


![image](https://github.com/IkChristine/Early-Diabetes-Prediction-with-Machine-Learning-Classification-algorithms/assets/104997783/28800408-d2aa-4e80-9e12-90b44af5b217)

* lower False positives (5) and False Negatives(5) in the logistic model


*  Accuracy score has gone up from 52% in dummy model to 90% in logistic model
*  Precision, recall and f1-scores have all increased as well
*  This means that the logistic model a better model to predict diabetes than the dummy classifier model

<p>&nbsp;</p>

### Decision Tree model

![image](https://github.com/IkChristine/Early-Diabetes-Prediction-with-Machine-Learning-Classification-algorithms/assets/104997783/77035792-ef93-4bc9-b1f8-53f8031dc824)

* The Decision Tree model identified 4 False Positive and Zero False Negative Values
* The Accuracy Score of the Decision Tree model is the highest at 95% compared to logistic regression model at 90%

<p>&nbsp;</p>

### Random Forest Model

![image](https://github.com/IkChristine/Early-Diabetes-Prediction-with-Machine-Learning-Classification-algorithms/assets/104997783/a7c3e8e1-68b8-48a1-b701-b159ca7a9bf4)

 * The Random Forest model identified 1 False Negative and 4 False Positive cases.
 * The Random Forest Classification model has an accuracy of 95%
 * This is slighly lower compared to the Decision tree regression model accuracy of 96%


## The overall best model in this analysis is the Decision tree at 95% prediction accuracy.
  
