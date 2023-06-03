# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.

2. Upload the CSV file in the compiler and read it.
 
3. Find head,info and null for the dataset.

4. Import KMeans and use it to plot the data in clusters.

5. End the Program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: NAVIN KUMAR J
RegisterNumber:  212222240071
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
### 1. data.head() function
![Output1](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/1e7b46f9-ea7f-4d2c-bdfa-e5f8c092cbcb)

### 2. data.info()
![Output2](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/6cac6a5f-9ed5-4b55-bad8-b3d4e4636af7)

### 3. data.isnull().sum() function
![Output3](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/155cf551-8138-400e-b90e-5f91b8bfa162)

### 4. Elbow method Graph
![Output4](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/cf0e2901-ee73-4b67-8f1e-f772fa485d0b)

### 5. KMeans clusters
![Output5](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/7fff8722-2221-44bd-94fa-70d22a17f28b)

![Output6](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/a8b54a85-5da8-4196-b7ca-4caa81933f2c)

### 6. Customer segments Graph
![Output7](https://github.com/SanthoshUthiraKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477975/b6bb583d-8a7c-4f4f-88de-64140a58f4b3)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
