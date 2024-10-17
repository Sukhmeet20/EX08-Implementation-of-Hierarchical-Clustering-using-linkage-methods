# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Compute the distance matrix between all data points.
2.Identify the two closest cluster and merge them.
3.Update the distance matrix to reflect the new cluster.
4.Repeat steps 2 and 3 until only one cluster remains.

## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: Sukhmeet Kaur G
RegisterNumber: 2305001032 
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage, fcluster
from sklearn.preprocessing import StandardScaler
df=pd.read_csv("/content/Hclus_EX8.csv")
df.head()
X=df[['StudentID','Marks']].values
X
Z=linkage(X,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dentogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student Segmented (Hierarchical Clustering)")
10/10/2024, 14:16 EX08-Implementation-of-Hierarchical-Clustering-using-linkage-methods/README.md at main · Madhumitha2006/EX08-Imple…
https://github.com/Madhumitha2006/EX08-Implementation-of-Hierarchical-Clustering-using-linkage-methods/blob/main/README.md 1/6
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
Z=linkage(X,method='single')
plt.figure(figsize=(5,2))
plt.title("Dentogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student Segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
```

## Output:
![Screenshot 2024-10-17 132327](https://github.com/user-attachments/assets/7e684ded-b597-4334-85bf-16ca4af41f8f)
![Screenshot 2024-10-17 132333](https://github.com/user-attachments/assets/563f1358-0043-4eb0-929f-b5757eaa343d)
![Screenshot 2024-10-17 132341](https://github.com/user-attachments/assets/a602fade-8609-4af9-9bab-bf8465126824)
![Screenshot 2024-10-17 132346](https://github.com/user-attachments/assets/a153f08e-0582-4f7a-a8db-a1d4677f3a6f)
![Screenshot 2024-10-17 132353](https://github.com/user-attachments/assets/aafb7299-0140-4bf3-a983-f0093b1f48cb)
![Screenshot 2024-10-17 132401](https://github.com/user-attachments/assets/2fcb6592-fc48-4754-a4a8-3a235d717034)
![Screenshot 2024-10-17 132408](https://github.com/user-attachments/assets/6ad03d46-6f14-4b37-b5c3-6dbf89dcc97c)
![Screenshot 2024-10-17 132527](https://github.com/user-attachments/assets/59e33887-cc07-4cf5-a802-cf847f7a5331)



## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
