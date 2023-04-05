# workshop-Multivariate-analysis
# AIM:
To Perform Multivariate Analysis
# ALGORITHM:
1.Read the given data

2.Get information from the data

3.Perform the Multivariate Analysis

4.Save the clean data to file
# PROGRAM:
```
Name:B.Roseline
Regno:212221220046
```
```
import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

import io

from google.colab import files

uploaded = files.upload()

dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv.csv']))

print(dd)
```
# Types of bivariate:
# 1. Numerical & Numerical
```
sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])
```
# ![image](https://user-images.githubusercontent.com/128909895/229968910-2243bda7-2ced-45fc-ac41-0e2b52d8aece.png)
# 2. Numerical & Categorical
```
sns.barplot (x=dd['Duration'],y=dd['Price'])
```
# ![image](https://user-images.githubusercontent.com/128909895/229969102-4d6e1a39-833d-46f4-ae2c-054dd31f53e5.png)
```
sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)
```
# ![image](https://user-images.githubusercontent.com/128909895/229969207-86ffbd68-5205-489c-991f-5a598b680cfb.png)
```
states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()

```
# ![image](https://user-images.githubusercontent.com/128909895/229970089-5364dc34-8f0e-42e2-849a-b037d358453c.png)
# Multivariate Analysis
```
dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()
```
# ![image](https://user-images.githubusercontent.com/128909895/229970290-46a5b383-f310-419b-ad54-eda32f61c8f7.png)
# RESULT:
Thus, Bivariate/Multivariate Analysis is performed successfully.
