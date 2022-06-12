# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries.
2. Upload the csv file and read the dataset.
3. Check for any null values using the isnull() function.
4. From sklearn.tree inport DecisionTreeRegressor.
5. Import metrics and calculate the Mean squared error.
6. Apply metrics to the dataset, and predict the output.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Senthil Kumar S
RegisterNumber:  212221230091
*/
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
y = data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2 = metrics.r2_score(y_test,y_pred)
r2
dt.predict([[2,2]])
```

## Output:

## Data Head:
![1](https://user-images.githubusercontent.com/93860256/173227142-95a4465f-626a-4d0b-a01b-2a61701d0090.PNG)


## Data Info:
![2](https://user-images.githubusercontent.com/93860256/173227155-221e4cc6-04f5-4614-8b5b-151c8edf5f58.PNG)


## Data Head after applying LabelEncoder():
![3](https://user-images.githubusercontent.com/93860256/173227160-ff818d57-dc23-42c3-bb55-6ea2652bc303.PNG)


## MSE:
![4](https://user-images.githubusercontent.com/93860256/173227163-80793db0-2b2d-4838-84c6-0a5353da7a22.PNG)


## r2:
![5](https://user-images.githubusercontent.com/93860256/173227170-bed07a5c-a621-45d9-a335-853c44ea044b.PNG)


## Data Prediction:
![6](https://user-images.githubusercontent.com/93860256/173227177-effc4f63-e511-4282-8a3d-da18681e8951.PNG)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
