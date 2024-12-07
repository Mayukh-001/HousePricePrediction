# Salary Prediction and Upgradation
AI to get salary updatation.


Salary Prediction & Update

Import Libraries

import pandas as pd
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt

Load Dataset from Local Directory

from google.colab import files
uploaded = files.upload()

Load Dataset

dataset = pd.read_csv('data2.csv')

Load Summarize

print(dataset.shape)
print(dataset.head(5))

Visualize Dataset

plt.xlabel('Level')
plt.ylabel('Salary')
plt.scatter(dataset.Level,dataset.Salary,color='red',marker='*')

Segregate Dataset into Input X & Output Y

X = dataset.drop('Salary',axis='columns')
X
Y = dataset.Salary
Y

Training Dataset using Linear Regression

model = LinearRegression()
model.fit(X,Y)

Predicted Price for Land sq.Feet of custom values

x=18
Salary=[[x]]
PredictedmodelResult = model.predict(Salary)
print(PredictedmodelResult)

Let's check is our model is Right ?
Theory Calculation
Y = m * X + b (m is coefficient and b is intercept)

m=model.coef_
print(m)
b=model.intercept_
print(b)

Y=mx+b

y = m*x + b
print("The Price of {0} Square feet Land is: {1}".format(x,y[0]))
