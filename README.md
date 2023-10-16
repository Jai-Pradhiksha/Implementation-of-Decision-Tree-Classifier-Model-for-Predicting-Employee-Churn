# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas library to read csv or excel file.
2. Import LabelEncoder using sklearn.preprocessing library.
3. Transform the data's using LabelEncoder.
4. Import decision tree classifier from sklearn.tree library to predict the values.
5. Find accuracy.
6. Predict the values.
7. End of the program.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: JAI PRADHIKSHA D P
RegisterNumber:  212221040062
*/
```

```
import pandas as pd
data=pd.read_csv("Employee.csv")
print("data.head()")
data.head()

print("data.info()")
data.info()

print("isnull() and sum()")
data.isnull().sum()

print("data value counts()")
data["left"].value_counts()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

print("data.head() for salary")
data["salary"]=le.fit_transform(data["salary"])
data.head()

x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()

y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
print("Accuracy value")
accuracy

print("data.prediction")
dt.predict([[0.5,0.8,9,260,6,0,1,2]])



```

## Output:
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/04c1b916-78f2-432a-8d37-c1cae08e44d1)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/81f7497e-6cca-40d9-9437-6bd75847c67e)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/4c084051-4799-43c2-bfe5-dd5f6c68875c)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/18372ec8-e540-4c7d-8916-642f9a6f71f3)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/1a85a152-3fdb-4d5a-b798-0bf91ef2efcf)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/ae134cc0-2382-4940-83d0-e725aefc3549)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/39a2725b-d7a8-4a77-8fd6-77b45a25a1d1)
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/100289733/cf2734dc-ecb2-4693-b7c2-61db259feef0)



## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
