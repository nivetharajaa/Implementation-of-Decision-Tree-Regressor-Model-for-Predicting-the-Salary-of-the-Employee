# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the required libraries.

2.Read the data frame using pandas.

3.Get the information regarding the null values present in the dataframe.

4.Apply label encoder to the non-numerical column inoreder to convert into numerical values.

5.Determine training and test data set.

6.Apply decision tree regression on to the dataframe.

7.Get the values of Mean square error, r2 and data prediction. 

## Program:
```
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Nivetha A
RegisterNumber:212222230101

import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data['Position']=le.fit_transform(data['Position'])
data.head()

x=data[['Position','Level']]
y=data['Salary']

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier()
dt.fit(x_train,y_train)
y_predict=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_predict)
mse

r2=metrics.r2_score(y_test,y_predict)
r2

dt.predict([[5,6]])

```

## Output:

### DATA HEAD

![image](https://github.com/nivetharajaa/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/120543388/7dd63c8d-c8fd-4101-866e-9424638d0c60)

### DATA INFO

![image](https://github.com/nivetharajaa/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/120543388/cb8e552d-05b5-4a55-be40-5cb730daa61a)

### Data Head after applying LabelEncoder():

![image](https://github.com/nivetharajaa/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/120543388/6777adc1-6d50-45c0-8ea3-97b5ad3eb0db)

### MSE:

![image](https://github.com/nivetharajaa/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/120543388/a010bdbd-df20-499f-88a3-47017a7b52d7)

### r2
![image](https://github.com/nivetharajaa/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/120543388/0efbc50e-8d81-4163-a8d0-6219b920cafa)

### Data prediction:

![image](https://github.com/nivetharajaa/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/120543388/4cfeacec-4a25-486b-998e-606d420e776c)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
