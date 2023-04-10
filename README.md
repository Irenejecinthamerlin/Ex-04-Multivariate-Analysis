# Ex-04-Multivariate-Analysis
# Aim:
To perform Multivariate EDA on the given data set.
# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# Algorithm:
# Step 1
Import the built libraries required to perform EDA and outlier removal.
# Step 2
Read the given csv file
# Step 3
Convert the file into a dataframe and get information of the data.
# Step 4
Return the objects containing counts of unique values using (value_counts()).
# Step 5
Plot the counts in the form of Histogram or Bar Graph.
# Step 6
Use seaborn the bar graph comparison of data can be viewed.
# Step 7
Find the pairwise correlation of all columns in the dataframe.corr()
# Step 8
Save the final data set into the file
# Program:
```
Name : Irene jecintha merlin R
Register Number : 212221040058

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# Output
# Data
## ![image](https://user-images.githubusercontent.com/128350225/230835857-0a250984-5c3e-4f15-a125-bd0dfb398a40.png)
# Data.info
## ![image](https://user-images.githubusercontent.com/128350225/230835970-f2ee3b37-25ff-4b75-a41e-8adb818be0a4.png)
# Data.describe
## ![image](https://user-images.githubusercontent.com/128350225/230836029-1d4d367e-8e9f-47be-a627-53837b52833a.png)
# Checking the null values and Cleaning it
## ![image](https://user-images.githubusercontent.com/128350225/230836163-3c4bc068-a8da-42a3-9fb4-a06f125c2209.png)
## ![image](https://user-images.githubusercontent.com/128350225/230837178-9227f2be-b284-45af-a589-ed9ae651a457.png)
# DATA TYPES
## ![image](https://user-images.githubusercontent.com/128350225/230836269-03d64e75-961b-465b-a4b1-bd206e27127c.png)
# SCATTER PLOT
## ![image](https://user-images.githubusercontent.com/128350225/230836326-2f4cec73-a02f-4dcc-a9f4-c0070b30eddd.png)
# BAR PLOT
## ![image](https://user-images.githubusercontent.com/128350225/230836393-8dadc364-eb37-4890-be17-f064b4c9d7d5.png)
## ![image](https://user-images.githubusercontent.com/128350225/230836541-3602214b-514b-4fdf-a9e2-e5ee90bdad68.png)
## ![image](https://user-images.githubusercontent.com/128350225/230836602-6237b9a9-9595-42a2-9470-daa13b889d3a.png)
## ![image](https://user-images.githubusercontent.com/128350225/230836689-76422dd6-aa2d-4430-9b4d-192932305732.png)
# CORRELATION COEFFICIENT INTERPRETATION
## ![image](https://user-images.githubusercontent.com/128350225/230836821-5d9c320b-41ce-4ab5-8016-6e27ea64c871.png)
# HEATMAP
## ![image](https://user-images.githubusercontent.com/128350225/230836886-5db60cd9-0e5d-4366-8802-fd868bbd5a95.png)
# Result:
Thus we have read the given data and performed the multivariate analysis with different types of plots.


