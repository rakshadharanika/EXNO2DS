# EX-NO : 2 DATA SCIENCE
# AIM:

To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:

The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
NAME  : V RAKSHA DHARANIKA
REF   : 212223230167
DEP   : AIDS
```

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/ed08e7ec-2d75-49a5-8309-803c97c32abc)
```
df.info()
```
![image](https://github.com/user-attachments/assets/5ea27162-c7a5-4a32-9635-763489531033)
```
df.shape
```
![image](https://github.com/user-attachments/assets/12f35cdf-dff6-48ec-b29a-a26f0d95f599)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/cb16ad91-5117-456d-b8f5-24056e00069a)


## Categorical data analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/57d8a38d-f56b-444d-a5e6-cb7a0aeb0620)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/d2b7ab92-1921-4a1c-a40a-2c9ea2ad7ee7)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/612cae74-ba52-4277-8d7a-1b735b45cc58)

```

sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/906a8963-fd3b-495f-b1e8-17bc9e5705c3)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/6f214069-a802-4379-bdef-985a8eea161e)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/0af10054-8fdf-42d9-aed8-93dd056443bc)

## Bivariate Analysis

```

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/2a6459b0-81c2-470e-bcd4-0e44969d8f97)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/d8a9efc0-9607-432f-8763-3756d7921aa8)
```

df.boxplot(column="Age",by="Survived")
```


![image](https://github.com/user-attachments/assets/9cd91e3b-1e3f-44db-8566-5ba511e5e066)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])

```

![image](https://github.com/user-attachments/assets/0a939ac0-9417-498d-b79e-d9be685e8fef)

```
sns.jointplot(x="Age",y="Fare",data=df)
```


![image](https://github.com/user-attachments/assets/e10345fc-eca6-4502-a1fa-eec430220b6b)


## Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```


![image](https://github.com/user-attachments/assets/acf973d1-945a-4c17-8691-4483e8b1df8e)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

```

![image](https://github.com/user-attachments/assets/e8061e86-cb48-45c3-b8fd-84b5a309548f)

## Co-relation
```
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
plt.show()

```

![image](https://github.com/user-attachments/assets/bd12d9b7-de5c-46d8-a9db-8fae6124808f)

```
sns.pairplot(df)
```

![last](https://github.com/user-attachments/assets/dedb81fb-d2ec-4ee3-bdcb-9e43956e8413)














# RESULT
 We have performed Exploratory Data Analysis on the given data set successfully.
