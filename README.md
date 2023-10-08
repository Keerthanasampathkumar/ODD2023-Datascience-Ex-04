```c
Developed by: KEERTHANA S
Register no: 212222230066
```

# ODD2023-Datascience-Ex-04
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
## STEP 1:
Import the built libraries required to perform EDA and outlier removal.

## STEP 2:
Read the given csv file

## STEP 3:
Convert the file into a dataframe and get information of the data.

## STEP 4:
Return the objects containing counts of unique values using (value_counts()).

## STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8:
Save the final data set into the file.

# PROGRAM:
## SuperStore.csv file:
```c
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (2).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
## diabetes.csv file:
```c
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:

### Data frame of SuperStore
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/4e5807bf-832b-4790-a769-18a49eebcf3c)

### Data information
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/05512813-38c5-4b99-86ce-1c143f273e7d)

### Data describing
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/d1fbafda-d007-4edd-81a4-1c61e9de46b0)

### Sum of null values
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/4383a3ec-2c27-486f-ac38-0800569dcbd9)

### After removing null values
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/f2e205a7-7d5c-413e-9686-1303dea2d82a)

### Scatter plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/36163f78-dc59-477c-971d-bf92f6d1d3fb)

### Bar plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/d3af027a-96c7-4d30-8b26-c903b7f8c3b3)

![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/28215fe5-77b1-4464-a49f-6d0d1325a95c)


### Box plot

![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/d40797fb-a173-4cc4-b209-b2aaee7421e3)


### Dist plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/1f265612-1b85-4263-afe5-aeb8d224a200)

### Correlation coefficient interpretation
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/a47fd3ed-4e69-4f4f-a63f-55a9472945b1)

### Heat map
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/c8da333b-b321-4fb9-bbcc-91567ae2294c)

### Data frame for diabetes
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/992f3a49-4070-4af1-b74c-a6e9009f9c93)

### Data information
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/8e728b5e-41ce-42da-8cbb-51e3ac061a8b)

### Describing a data set
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/40282599-9060-4aef-9ed4-83c0ee7926bd)

### Sum of null values
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/ff19685a-0e73-4b54-b255-81478a3fb8f3)

### Scatter plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/8fdfeb9e-7a08-42d9-bcd9-8afac840e47b)

![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/a5b8bd72-8e9c-45ed-b880-63030db9926f)

### Bar plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/86d6b29a-2dda-47ef-aea3-52ce77ff77b0)

![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/216f47b3-bfc6-4801-b4e4-21d45aeae034)

### Box plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/f025a7e9-75ad-488f-8136-3831ec79b141)

### Dist plot
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/1ef8ba99-a325-4b1c-b298-87f69635edb2)

### Correlation coefficient interpretation
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/40bc830a-a19b-4d92-9f40-6cd264205cbd)

### Heat map
![image](https://github.com/Keerthanasampathkumar/ODD2023-Datascience-Ex-04/assets/119477890/ac458fae-fe44-462f-a30c-9ede99e39794)

# RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
