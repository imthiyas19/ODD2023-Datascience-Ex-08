# Ex-08-Data-Visualization-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
# READING THE GIVEN FILES:
```
import pandas as pd
df=pd.read_csv("/content/Superstore.csv",encoding='unicode_escape')
df.head()
```
# DATA VISUALIZATION USING SEABORN :
```
import seaborn as sns
from matplotlib import pyplot as plt
```
# LINE PLOT:
```
plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')
```
![283037689-5b7c067f-0e23-40aa-80de-7f2d5302e4c2](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/11ef6f7e-2afc-4120-b83f-48091af009ba)





![283037736-647cd99b-b826-4cc2-a394-f507826eb039](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/d3aacaf3-36fb-4e7c-beb1-715efaef0655)




![283037751-9926a587-ccd9-4efb-8d6f-9d0780584047](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/cb522e09-cc98-423d-9a01-28a5a40bc92b)


# SCATTERPLOT:
```
sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
```




![283037855-45bac79a-8503-4915-b8a5-eff1ac4aa74f](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/8a2a6eaf-6883-49ae-96f4-37f080adda57)


![283037867-bdd2e9e6-b475-4b86-b43b-196c76fd6955](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/2bea2045-6611-4ea3-83dc-b39a54bf4906)



![283037873-1e05cfdd-bdc7-4148-aa7b-8aa3abf004c0](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/14993cc3-900f-47c2-b386-7ddc01a86f55)



# BOXPLOT:
```
sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)
```


![283038030-2ea9b4c8-0239-46e6-bff5-4f4259b72b7e](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/60e940ba-7cf4-40c9-97f5-249410a4fff0)

![283038044-36f3813b-e346-4c78-87e3-39c5ac84063c](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/cc96ccbc-3257-4d89-875e-d48eb90faf3b)





# VIOLIN PLOT:
```
sns.violinplot(x="Profit",data=df)
```


![283038107-4ec8059c-98b1-4c71-bc8e-103b184e2102](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/6f8b5dc5-6850-498c-b167-2034d0b42e96)



# BARPLOT:
```
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
```


![283038360-1cd40ef2-0db1-47bb-af9e-f738d26d9274](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/0e94cdbe-008d-4a07-9172-b5099a1f6cbb)



![283038368-a9697bcc-b74d-41f2-9604-d3b413c03f4c](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/48484d09-b28b-493f-b1e9-f29d7c392446)



# POINTPLOT:

```
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```





![283038449-7972bf63-b1f7-4c81-8032-105feec6ea85](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/208ed406-02b5-4fea-b8e8-b1e536ea2784)




# COUNT PLOT:
```
sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)
```





![283038618-bf755632-d070-44ef-89ed-a4e02407eafa](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/2e4f78a1-685d-4d0c-8c26-6239b060b976)




![283038623-6ec64084-d8cd-448b-af80-d748e4e26d6d](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/a0715cd7-e5e5-4e73-93e5-cfec23a03896)




# HISTOGRAM :
```
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```



![283038747-ef08582c-01d9-406c-8921-67c3154b3682](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/6c3fe3d1-4f54-4b47-a63f-c9f883b08fa0)



# KDE PLOT:
```
sns.kdeplot(x="Profit", data = df,hue='Category')
```


![283039108-b3d5ffaf-9ea3-4318-a1d4-994022dc27da](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/5cd5eb49-c3e7-401b-9036-d4a0bc597e84)



# DATA VISUALIZATION USING MATPLOTLIB :
# PLOT :
```
plt.plot(df['Category'], df['Sales'])
plt.show()
```
![283039341-2cb34f9e-eb14-4126-882c-f25c3fcc5e82](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/35d5b78e-7edb-4817-a799-366187abc0f6)



# HEATMAP :
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```




![283039453-24349829-7af9-404b-95b3-2eba14b77981](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/7555fdbe-2b80-46c3-a40f-062918e442e2)





# PIECHART:
```
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
```



![283039568-b2a276ac-79b7-4b0c-8471-03516635a5d8](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/0a26cc4e-d820-4c51-9ca8-25d15488113a)





![283039578-8a4dea98-9c1d-4c22-acbc-68acf1f2838d](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/66897085-ce94-49a6-8f13-ef6404debca6)



## HISTOGRAM:
```
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
```



![283039692-3d9f14f8-225b-4206-a149-da5a2ee2f555](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/5c65e33f-e7e7-4173-bd22-59a6cc9a5c97)

# BARGRAPH:
```
plt.bar(df.index,df['Category'])
plt.show()
```



![283039785-d7a43426-dac2-4c4a-b251-2cefb1cf2ef2](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/81f2e58d-2afd-4ff0-a998-3d7556ff3ed4)




# SCATTERPLOT:
```
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
```




![283039866-ea53e5b3-99e7-44b6-b956-bbee44ce7412](https://github.com/imthiyas19/ODD2023-Datascience-Ex-08/assets/120353416/b5a5bcbe-a640-47f7-be57-fa81868a35ae)



# BOXPLOT:
```
plt.boxplot(x="Sales",data=df)
plt.show()
```










# RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
