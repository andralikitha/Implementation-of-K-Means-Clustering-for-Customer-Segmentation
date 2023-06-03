# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.
2. Initialize and print the data.head(),data.info(),data.isnull().sum()
3. Import sklearn.cluster import KMeans
4. Calculate the value of KMeans Clusters.
5. Plot the graph from Elbow method and find y_pred values .
6. Plot the graph from Customer Segments Graph.


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Andra likitha
RegisterNumber:  212221220006
*/
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")

print("data.head() function:")
data.head()

print("data.info():")
data.info()

print("data.isnull().sum() function:")
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[] #Within-Cluster Sum of Square.

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  
print("Elbow method Graph:")
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

print("KMeans clusters:")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

print("y_pred:")
y_pred=km.predict(data.iloc[:,3:])
y_pred

print("Customer segments Graph:")
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



## Output:

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/090892af-3697-4485-b745-2ba9c497aba5)

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/02055079-3ef8-44a8-a819-bfac03fe2bac)

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/1fa88ff4-a4d4-47c0-96ec-b7baef003480)

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/85a71a05-d1b2-4232-a567-2c4a3b2cb05e)

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/663d335b-5991-413a-9c83-faaaf9188922)

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/8d4b1060-28f6-4f70-aea5-7d4ebafafc12)

![image](https://github.com/andralikitha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131592130/0d1047a2-9213-4b64-8ebf-d86ad5c51533)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
