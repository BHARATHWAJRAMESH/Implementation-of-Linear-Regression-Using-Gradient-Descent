# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Use the standard libraries in python for Gradient Design.

2.Upload the dataset and check any null value using .isnull() function.

3.Declare the default values for linear regression.

4.Calculate the loss usinng Mean Square Error.

5.Predict the value of y. 6.Plot the graph respect to hours and scores using scatter plot function.


## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: BHARATHWAJ R
RegisterNumber: 212222240019
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

data=pd.read_csv('/content/ex1.txt',header = None)

plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("population of city (10,000s)")
plt.ylabel("profit ($10,000)")
plt.title("profit prediction")

def computeCost(X,y,theta):
  m=len(y)
  h=X.dot(theta)
  square_err=(h-y)**2
  return 1/(2*m) * np.sum(square_err)

data_n=data.values
m=data_n[:,0].size
X=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))

computeCost(X,y,theta)

def gradientDescent(X,y,theta,alpha,num_iters):

  m=len(y)
  J_history=[]

  for i in range(num_iters):
    predictions = X.dot(theta)
    error = np.dot(X.transpose(),(predictions -y))
    descent = alpha * 1/m * error
    theta -= descent
    J_history.append(computeCost(X,y,theta))

  return theta,J_history

theta,J_history = gradientDescent(X,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1")

plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Gradient Descent")

plt.scatter(data[0],data[1])
x_values=[x for x in range(25)]
y_values=[y*theta[1]+theta[0] for y in x_values]
plt.plot(x_values,y_values,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")

def predict(x,theta):
  predictions = np.dot(theta.transpose(),x)
  return predictions[0]

predict1=predict(np.array([1,3.5]),theta)*10000
print("For Population = 35,000, we predict a proft of $"+str(round(predict1,0)))

predict2=predict(np.array([1,7]),theta)*10000
print("For population = 70,000, we predict a profit of $"+str(round(predict2,0)))
/*
```

## Output:
Profit prediction:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/9a644056-8097-4495-9bc3-904287d93cc5)

Function output:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/df827236-4cd2-40b9-8916-9873d7bc9a1c)

Gradient descent:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/f27f6010-0b65-4bd5-b1c2-baf04181ae58)

Cost function using gradient descent:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/56bc419e-f053-4f3c-bc0c-6a2ef81a15e6)

Linear regression using profit prediction:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/59d1b0e1-2930-4910-8651-2ef0f1fb159f)

Profit prediction for a population of 35000:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/a69b5541-ffa9-448a-abfb-48b6f84b93fa)

Profit prediction for a population of 70000:

![image](https://github.com/BHARATHWAJRAMESH/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119394248/d7269c85-9183-4b35-b760-915482ebc475)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
