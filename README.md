# Name:Manimaran V
# Reg.no.212224220060
# Exno:2 -Exploratory Data Analysis
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
```py
 import pandas as pd
      import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![Screenshot 2025-03-25 104957](https://github.com/user-attachments/assets/50ca7829-73a6-4bd1-9349-a79d09d0d5c6)

```
py
df.info()
```
![Screenshot 2025-03-25 105036](https://github.com/user-attachments/assets/05893d6c-4337-4b28-a249-13baf1d45454)

```
py
df.shape
```
![Screenshot 2025-03-25 105111](https://github.com/user-attachments/assets/a6417b67-3f0e-4d18-8cb6-401569dd3ef8)

```
py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2025-03-25 105147](https://github.com/user-attachments/assets/84ec1f05-1b2b-411a-a830-b62f2ea84b9e)

```
py
df.shape
```
![Screenshot 2025-03-25 105226](https://github.com/user-attachments/assets/5521ba62-9de0-4bc0-809f-c24430f1cb98)


### Categorical data analysis
```py
df.nunique()
```
![Screenshot 2025-03-25 105304](https://github.com/user-attachments/assets/6a25fb03-fac2-48f9-b58a-7f9a7a546421)

```
py
df["Survived"].value_counts()
```
![Screenshot 2025-03-25 105342](https://github.com/user-attachments/assets/82fa9864-a8d0-4ca9-8121-8fcb522ad648)
```

py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-25 105415](https://github.com/user-attachments/assets/9b957666-4640-4045-8bf8-ee56664f10b8)

```
py
sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-25 105447](https://github.com/user-attachments/assets/37ff513d-d632-4817-a38a-ab714b3e03eb)
```
py
df.Pclass.unique()
```
![Screenshot 2025-03-25 105536](https://github.com/user-attachments/assets/7d11ade4-8898-42b3-8e30-32deff38092f)

```
py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-25 105623](https://github.com/user-attachments/assets/ece2fecb-0477-4323-8295-a124c247cf8a)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-25 105705](https://github.com/user-attachments/assets/450db4eb-77b4-450a-8e8d-d03e3caa739e)

```
py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-25 105733](https://github.com/user-attachments/assets/abd28720-8f24-4051-9a24-b9687ac3fe09)

```
py
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-25 105801](https://github.com/user-attachments/assets/c1599189-7cc6-419a-9f96-e221e3e86935)

```
py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2025-03-25 105828](https://github.com/user-attachments/assets/c05ee667-38f3-431f-944b-f3494ca2d0f6)

```
py
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-25 105913](https://github.com/user-attachments/assets/180c8211-21fa-41b7-9da3-20a7c7af5d02)


### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2025-03-25 105952](https://github.com/user-attachments/assets/f762d341-323e-4e7f-b898-fd8b2430e959)

```
py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-25 110138](https://github.com/user-attachments/assets/67d5168f-1aeb-42e5-8dba-b4d6e2f6cf08)


# Co-relation
py
corr=df.corr()
sns.heatmap(corr,annot=True)

![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/6ad0bc8d-58a7-4093-8ba3-60b4cc8b2a3c)

py
sns.pairplot(df)

![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/43a838dc-8765-4c1b-9f81-c1d53d853265)
# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
