# Implementation of Decision Tree Regressor Model for Predicting the Salary of the Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.  Import dataset and get dataset info
2. check for null values
3. Map values for position column
4. Split train data and test data
5. Import decision tree regressor and fit it for data
6. Calculate mse r2 and y_predict

## Program:
```txt
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Krupa Varsha P
RegisterNumber:  212220220022
```
```python3
import pandas as pd 
df=pd.read_csv('/content/Salary.csv') 
df.head()
```
```python3
df.info()
```
```python3
df.isnull().sum()
```
```python3
from sklearn.preprocessing import LabelEncoder 
le=LabelEncoder() 
df["Position"]=le.fit_transform(df["Position"])
df.head()
```
```python3
x=df[["Position","Level"]] 
y=df[["Salary"]]
```
```python3
from sklearn.model_selection import train_test_split 
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
```
```python3
from sklearn.tree import DecisionTreeRegressor 
dt=DecisionTreeRegressor() 
dt.fit(x_train,y_train) 
y_pred=dt.predict(x_test) 
from sklearn import metrics 
mse=metrics.mean_squared_error(y_test,y_pred) 
mse
```
```python3
r2=metrics.r2_score(y_test,y_pred) 
r2
```
```python3
dt.predict([[5,6]])
```

## Output:

![95aaa890-6de1-4e8d-866e-ae6e5218e654](https://github.com/Krupa-Varsha-P/ML_7/assets/100466625/0309b4e2-531a-4faf-a3a8-623cb27015d0)
![6417f102-73fa-4fb1-90a1-7d9bf25b717f](https://github.com/Krupa-Varsha-P/ML_7/assets/100466625/0fbfe11a-3229-42d6-8e52-e906f800b6af)
![167306ea-5f12-48f5-9cd9-b1e2534909fc](https://github.com/Krupa-Varsha-P/ML_7/assets/100466625/afe15bf3-2fdc-40a0-8201-1aa27b28935a)
![1d86189b-6d81-46a1-8884-7c7efc52a77d](https://github.com/Krupa-Varsha-P/ML_7/assets/100466625/d884323b-a751-4ccd-bd42-c67638725ebc)
![b1085a0e-89a4-41c2-bf1e-71245fbcc10c](https://github.com/Krupa-Varsha-P/ML_7/assets/100466625/2b996cfa-cf52-41e4-9250-41b611df8473)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
