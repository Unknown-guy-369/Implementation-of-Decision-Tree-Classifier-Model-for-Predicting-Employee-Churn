# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. **Import and Load Dataset**
   - Load the dataset using `pandas.read_csv()`.
   - Display initial records and check for missing values.

2. **Preprocessing**
   - Encode the categorical feature `salary` using `LabelEncoder`.

3. **Feature and Target Selection**
   - Select relevant features (`x`) and target (`y`) for training.

4. **Split the Dataset**
   - Use `train_test_split()` to divide the data into training and testing sets.

5. **Model Training**
   - Initialize and train a `DecisionTreeClassifier` with `criterion="entropy"`.

6. **Prediction and Evaluation**
   - Predict using the test set and evaluate the accuracy using `accuracy_score`.
   - Make prediction for a new sample input.
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Abishek Priyan M
RegisterNumber: 212224240004
*/
```
```py
import pandas as pd
df=pd.read_csv("Employee.csv")
df.head()
df.isnull().sum()
df["left"].value_counts()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
df["salary"]=le.fit_transform(df["salary"])
df.head()
x=df[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","left","promotion_last_5years","salary"]]
x.head()
y=df["left"]
y.head()
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=45)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)

from sklearn.metrics import accuracy_score
y_pred=dt.predict(x_test)
accuracy=accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2,2]])
```

## Output:
 ### Dataset
 ![image](https://github.com/user-attachments/assets/365604dd-f37e-4e5a-acef-190b9f4386bf)

 ### Null values
 ![image](https://github.com/user-attachments/assets/0bb69286-36c7-4268-b0c3-3feb8e098d5e)

 ### Class Distribution
 ![image](https://github.com/user-attachments/assets/153f5982-1117-4ba0-b09c-0580a3cab0ed)

### Encoded Categorical Feature

![image](https://github.com/user-attachments/assets/0a06cdc6-b53d-4b53-81ff-70d53e36108e)

![image](https://github.com/user-attachments/assets/afc0066f-a9e2-4a35-850e-ff2c83496742)

![image](https://github.com/user-attachments/assets/91d3e43f-3fcd-4f3a-b3c4-662e9e2c1c11)

### DecisionTree Classifier
![image](https://github.com/user-attachments/assets/93c63c95-47f4-4acd-9824-148ea3633a8a)

### Accuracy
![image](https://github.com/user-attachments/assets/fb97c39e-96da-4a17-b406-64a7ee7f1b3f)

### Sample Predict
![image](https://github.com/user-attachments/assets/7dba90de-63f6-4112-9d97-50638e497f43)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
