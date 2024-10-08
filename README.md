# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard Libraries.
2.Set variables for assigning dataset values.
3.Import linear regression from sklearn.
4.Assign the points for representing in the graph.
5.Predict the regression for marks by using the representation of the graph.

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by:Roop Sagar S L
RegisterNumber:212223040175
*/

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error,mean_squared_error
df=pd.read_csv('student_scores.csv')
print(df)
df.head(0)
df.tail(0)
print(df.head())
print(df.tail())
x = df.iloc[:,:-1].values
print(x)
y = df.iloc[:,1].values
print(y)
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(x_train,y_train)
y_pred = regressor.predict(x_test)
print(y_pred)
print(y_test)
#Graph plot for training data
plt.scatter(x_train,y_train,color='black')
plt.plot(x_train,regressor.predict(x_train),color='blue')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
#Graph plot for test data
plt.scatter(x_test,y_test,color='black')
plt.plot(x_train,regressor.predict(x_train),color='red')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_absolute_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('MAE = ',mae)
rmse=np.sqrt(mse)
print("RMSE= ",rmse)

```


## Output:

![307237070-7c8d0f44-399a-4a52-9109-be17c60e642f](https://github.com/user-attachments/assets/ef06416a-ae17-4ac8-beb6-962e0bbcc33a)

![307237103-29810b1e-0781-4338-a6ba-b7b8e2d30316](https://github.com/user-attachments/assets/d8d28ea2-0a9d-416d-b334-650af01f432e)

![307237103-29810b1e-0781-4338-a6ba-b7b8e2d30316](https://github.com/user-attachments/assets/022f197b-1dd5-4662-805f-15b04b19a86b)

![307237178-6e3d9021-fbe2-421f-a1bc-2902ccd99ff5](https://github.com/user-attachments/assets/92974252-ff5d-467a-b644-47a77e947a69)

![307237178-6e3d9021-fbe2-421f-a1bc-2902ccd99ff5](https://github.com/user-attachments/assets/ee3a9299-90e7-4d0d-aa02-9b0ea3da7b94)

![307237218-6574b4f6-3e55-4ff6-9e1e-35b78c86ec66](https://github.com/user-attachments/assets/7ff408d2-e439-4cd1-9e59-30ae5e212cae)

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
