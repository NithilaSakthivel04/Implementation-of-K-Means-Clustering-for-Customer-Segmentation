# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
 

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by : NITHILA S
RegisterNumber : 212224040224
```

```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
### head()
<img width="960" height="277" alt="Screenshot 2025-11-11 153102" src="https://github.com/user-attachments/assets/5b412b90-5a9c-4895-ba34-ae697cef16a9" />

### info()
<img width="942" height="361" alt="Screenshot 2025-11-11 153110" src="https://github.com/user-attachments/assets/564356ba-8b65-4ac0-815e-d3e54a2dcbfb" />

### isnull.sum()
<img width="1124" height="174" alt="image" src="https://github.com/user-attachments/assets/d0072b9a-b4bf-4526-bdfb-9eef5ac3975c" />

### Elbow method
<img width="1313" height="674" alt="image" src="https://github.com/user-attachments/assets/75463b01-a64d-4dbe-af7f-44ef33420344" />

### Fitting the no. of clusters
<img width="645" height="75" alt="image" src="https://github.com/user-attachments/assets/8194bcda-b1a0-4026-9eee-d7463253c044" />

### Prediction of Y
<img width="935" height="239" alt="image" src="https://github.com/user-attachments/assets/67953175-31d9-4465-b0f0-192c0c73e17e" />

### Customer Segments
<img width="1120" height="645" alt="image" src="https://github.com/user-attachments/assets/da1dd53c-9f13-4014-a769-af2da07d7772" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
