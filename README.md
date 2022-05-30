# EX:08 DATA VISUALIZATION
## AIM:
To Perform Data Visualization on a complex dataset and save the data to a file.

## EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM:
### STEP 1
Read the given Data.

### STEP 2
Clean the Data Set using Data Cleaning Process.

### STEP 3
Use libraries like Seaborn and Matplotlib.

### STEP 4
Apply data visualization techniques to identify the patterns of the data.

## CODE:
```
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram


plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```
## OUTPUT:
### Reading the given dataset:
![pic1](https://user-images.githubusercontent.com/93427278/170985646-ccfbc412-b358-4115-b197-70e373a97404.png)

## Data Visualization Using Seaborn:
### 1.Lineplot 
![pic2](https://user-images.githubusercontent.com/93427278/170985803-c6671117-ccfb-4a94-8132-8e1a258d1593.png)
![pic3](https://user-images.githubusercontent.com/93427278/170985838-de8ed4fd-65a9-43ec-a3a0-9bf04017fe45.png)

### 2.Scatterplot 
![pic4](https://user-images.githubusercontent.com/93427278/170985871-d2732de8-a729-4e59-af26-0868e29d7f3d.png)
![pic5](https://user-images.githubusercontent.com/93427278/170985891-e19a83d9-2cd2-40b0-939f-01ef0decec37.png)

### 3.Boxplot
![pic6](https://user-images.githubusercontent.com/93427278/170985937-0a3b5dae-0306-4d45-b8d4-c278620c2e48.png)
![pic7](https://user-images.githubusercontent.com/93427278/170985949-9876aa03-940d-434c-a5cc-b830845e97b3.png)

### 4.Violinplot 
![pic8](https://user-images.githubusercontent.com/93427278/170985994-1b57705e-e411-43ee-8553-b20656e1a7cd.png)

### 5.Barplot 
![pic9](https://user-images.githubusercontent.com/93427278/170986074-e320e391-d31c-458d-9007-a2a9b4930b71.png)
![pic10](https://user-images.githubusercontent.com/93427278/170986095-986ef622-5254-4228-ab6c-0cdba8cf389f.png)

### 6.Pointplot 
![pic11](https://user-images.githubusercontent.com/93427278/170986140-34e896cd-9265-4cc1-98ca-73eb1b600028.png)

### 7.Countplot 
![pic12](https://user-images.githubusercontent.com/93427278/170986183-c1fe579c-484c-499a-939f-ea5502ba930b.png)

### 8.Histogram 
![pic13](https://user-images.githubusercontent.com/93427278/170986236-7d0f5c48-3caa-4b3b-a44a-2613bd777220.png)

### 9.KDE Plot 
![pic14](https://user-images.githubusercontent.com/93427278/170986290-28e2e3f7-1e19-4ca1-bf30-7a9a1e133ac5.png)

## Data Visualization Using Matplotlib:
### 1.Plot 
![pic15](https://user-images.githubusercontent.com/93427278/170986355-98ec623d-13b3-4d26-8448-4d1320ffe290.png)

### 2.Heatmap 
![pic16](https://user-images.githubusercontent.com/93427278/170986395-34027063-a756-4307-a144-7d9e51554528.png)
![pic17](https://user-images.githubusercontent.com/93427278/170986410-eaa8366c-70fc-4bba-b212-8dfd53b39c03.png)

### 3.PieChart 
![pic18](https://user-images.githubusercontent.com/93427278/170986466-330ceaec-c3f0-40ab-a177-92885454b26b.png)
![pic19](https://user-images.githubusercontent.com/93427278/170986481-42e9f0ec-5223-4a87-a553-a649a30a2384.png)

### 4.Histogram 
![pic20](https://user-images.githubusercontent.com/93427278/170986533-19a5064d-9acf-456a-adc3-ec4ecdb4765b.png)

### 5.Bargraph 
![pic21](https://user-images.githubusercontent.com/93427278/170986583-f76c12d8-735f-4f9a-977d-3931e5465ca3.png)

### 6.Scatterplot 
![pic22](https://user-images.githubusercontent.com/93427278/170986638-2d06d57b-9b6c-468f-b992-5ad1107b8982.png)

### 7.Boxplot 
![pic23](https://user-images.githubusercontent.com/93427278/170986701-51425ca2-db20-4b3e-bb79-73c3cfdcd2c8.png)

## RESULT:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
