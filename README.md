# Patient demographics and the prevalence of Stroke

![shutterstock_118491940](https://user-images.githubusercontent.com/119267803/224447689-ca6777bd-b565-4809-a3b3-805402a2f3d4.jpg)

### Data Source: 
https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset?resource=download
Attribute Information
1) id: unique identifier
2) gender: "Male", "Female" or "Other"
3) age: age of the patient
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
6) ever_married: "No" or "Yes"
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
8) Residence_type: "Rural" or "Urban"
9) avg_glucose_level: average glucose level in blood
10) bmi: body mass index
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
12) stroke: 1 if the patient had a stroke or 0 if not
*Note: "Unknown" in smoking_status means that the information is unavailable for this patient

## Every 40 seconds someone in the USA has a Stroke (CVA= Cerebral vascular Accident).
A stroke is when there is an interuption in the flow of blood to brain cells, this can be due to a blockage or a rupture of important blood vessles of the brain 

### Every 3 1/2 minutes someone dies of a stroke. 

### Every year over 790k people die due to a stroke 
### 610,000 of these deaths by stroke are their first occurance. 

World wide, 1 in 4 people will have a stroke in their life time, it's one of the leading causes of death in the USA due to its high mortality rate. And those that do survive face many logn term and permanent residuals like cognitive impairment, loss of basic motor functions, dysphasia and aphasia (loss of the ability to speak) and the ability to care for themselves. It is a sad and expensive disease to suffer from, so in disease research we try to get ahead of the curve by noticing trends in the data of the diseased to see if we can beef up preventative care for this and othe horrible diseases. In this data set we will explore features that have a high correlaton to the occurance of stroke and devise medicine management and treatment plans around the health issues  detected to avoid the progression into stroke. 

![image](https://user-images.githubusercontent.com/119267803/224454250-aa1a8dcd-9d9b-4abf-9090-d50f539f02c4.png)

The above mentioned heat map is a display of disease related features, like age, bmi, average glucose etc. These features all have been documented as risk factors tot he occurance of stroke, and we will see how much these features correlate and how we can beef up our patient screening process for better prevantative care. 

![image](https://user-images.githubusercontent.com/119267803/224456560-1c237f00-990c-4e10-afd9-91d2c5f64d93.png)

*The above bar plot indicated that most people have an average bmi observed but the outliers with bmi's over 30 had all experienced some sort of CVA event. Also those who hadnt suffered a stroke(0) has a lower minimun BMI at baseline*


The 2 biggest features that had the highest correletion to the occurance of stroke were bmi, and average glucose level. Even in graphs where these werent the focus it was easy to see that the patients with the out of range glucose levels (150<) and bmi's (over 30) all had experinced strokes. 

![image](https://user-images.githubusercontent.com/119267803/224457523-9d472f33-f6e1-47f0-a61a-eb8cdc8231e5.png)


In this above graph, is documenting patients that smoke, however everyone that smoked hasnt had a stroke but everyone with impaired glucose 150< all had experienced a stroke. 


Medical Data can be hard to handle because even though were tryign to prevent illness, the majority class is the healthy.And with this it can lead to class imbalances. I ran a baseline model, KNN model and logistic Regression models. The first 2 (baseline model and KNN) has accuracy of 95% however it was hightly biased with getting 100 to predict a healthy patient but totally missing the stroke victims. This is very dangerous because the identification and treatment of stroke is a matter of life or death. 

The model I would chose for production would be Logistic regression. Medical data tends to come very unbalanced, and while the other models " performed better" they were highly biased favoring the majority class which were the healthy patients whos information was recorded. While a " high" accuracy is important the macro average, weighted average, and recall all were better on this model:

precision    recall  f1-score   support

           0       0.99      0.73      0.84      3645
           1       0.14      0.83      0.24       187

    accuracy                           0.74      3832
    
   macro avg       0.56       0.78       0.54       3832
   
weighted avg       0.95        0.74       0.81         3832


showing me it was better at analyzing what was needed to predict the occurance of stroke vs the other biased models. Also Logistic regression has better parameters to handle class imbalances so the model can keep on improving and learning the more data re introduce to it until we are in the high 90's on accuracy without bias.



## Action plan

With the above mentioned data we will take a few courses of action regarding trying the trends seen and their correletion to the development of a stroke.

* BMI seems to play a large role in the occurance of stroke. All the people who suffered a stroke besides the children were all obese (BMI over 30). There seems to be decent nexus and it would be advisable to push movement and weight management services with our patients to bring down the overall BMI and hopefully minimize the occurance of stroke.

* Glucose also played a role as well with everyone who didnt suffer froma stroke having a normal glucose level (100<) vs everyone who suffered from a stroke has abnormal glucose (150<). This leads me to believe that a lot of people in this group might have undiagnosed or not well treated diabetes. We need to be more diligent in diabetes screenings of patients and when identified getting the patient on some sort of medication management to bring down the glusoce level.

* Hypertension, heart disease seem to go very hand in hand when observed against the occurance of stoke, the number of patients with hypertension, heart disease all seem to also be stroke victims, Once a patient is diagniosed with either of these they should be put on a watch list. They should be getting their labs checked eveyr 3 months for decline as well as medications to help handle the hypertension and heart disease.


With proper evaluation and watching of patient vitals and current diagnosed ailments, we can hopefully get ahead of the curve and prevent further decline in health of our patients due to CVA (strokes)
