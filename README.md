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
       ```
       import pandas as pd
       import numpy as np
       import matplotlib.pyplot as plt
       import seaborn as sns
       ```
       ```
       df=pd.read_csv("/content/titanic_dataset.csv")
       df
       ```
       ![{F45433A9-AA76-40CB-B683-47DF461CF9AD}](https://github.com/user-attachments/assets/6afd80cb-1871-4a29-ad3c-351cdda728f3)
       ```
       df.info()
       ```
       ![{F5B07D21-F3D7-452E-9A8D-8FCC38C2284C}](https://github.com/user-attachments/assets/d460ffee-40a5-4698-aee0-cb346dc7257d)
       ```
       df.shape
       ```
       ![{236811E4-504D-405F-9E57-B91CEB8ABAED}](https://github.com/user-attachments/assets/4ac7fd20-a2d2-4fbc-84d9-ab5fce43bd96)
       ```
       df.describe()
       ```
       ![{247822CF-D4E6-4EAF-A2D2-C06508677664}](https://github.com/user-attachments/assets/f472ce53-187c-437c-9fbe-7e7e1719b7eb)
       ```
       df.nunique()
       ```
       ![{47610618-B827-4B92-A522-6E81A09834E3}](https://github.com/user-attachments/assets/74a2f927-8b5f-4971-a07f-64beb0239767)
       ```
       df["Survived"].value_counts()
       ```
       ![{F159C3D1-6FFA-4FA8-9BFE-3ECB1DEF422D}](https://github.com/user-attachments/assets/09635075-1b26-4ed8-a909-794c756607a7)
       ```
       per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
       per
       ```
       ![{DA26726F-EDF0-47F7-9AA2-68D8ABB6CD5C}](https://github.com/user-attachments/assets/f83f3d81-3656-486e-a21f-dc1ec1f3e15e)
       ```
       sns.countplot(data=df,x="Survived")
       ```
       ![{59DF17DE-E7D4-4C2E-830D-A986D39CB683}](https://github.com/user-attachments/assets/23bb0966-41c3-4a54-b954-9b93385a68e2)
       ```
       df.Pclass.unique()
       ```
       ![{BF820408-D514-4418-9EA0-FEF3AFB95884}](https://github.com/user-attachments/assets/313fa398-636e-49e5-b0e4-5be8562bd787)
       ```
       df.rename(columns={'Sex':'Gender'},inplace=True)
       df
       ```
       ![{80B9EA4D-3BBE-40EE-84BC-BFE273C268DB}](https://github.com/user-attachments/assets/bfdb3923-c1df-44d4-b8ff-2393d8135f09)
       ```
       sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
       ```
       ![{59029811-F31D-4C2A-AB4A-A516DAF5CB8E}](https://github.com/user-attachments/assets/4cf370a8-c362-458a-92e5-84de04ab891e)
       ```
       sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
       ```
       ![{CE93E61B-501D-440C-91BB-3BA001435694}](https://github.com/user-attachments/assets/b32c6252-46a4-4d9c-a9a7-8b2cbd754910)
       ```
       df.boxplot(column="Age",by="Survived")
       ```
       ![{12CD1C70-A244-4DB5-9E2B-D0EA5958C148}](https://github.com/user-attachments/assets/72e9d276-d173-4a9d-95f4-f540a6ef9df6)
       ```
       sns.scatterplot(x=df["Age"],y=df["Fare"])
       ```
       ![{E4713A0E-0CE2-423F-8227-DF0F5862C9CD}](https://github.com/user-attachments/assets/8abf2b47-f7d3-4a08-96c0-5ad6c5428f92)
       ```
       sns.jointplot(x="Age",y="Fare",data=df)
       ```
       ![{67B41037-5C48-4C6C-90E1-9FD456CD4F29}](https://github.com/user-attachments/assets/664c99d9-49fc-4a6d-a5ad-90906e7d77e9)
       ```
       fig, ax1 = plt.subplots(figsize=(8,5))
       plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
       ```
       ![{742D9F6E-095B-4689-8285-7FEF1D0BAFA6}](https://github.com/user-attachments/assets/630f4961-b7ce-4195-bd8e-ba1addd600e0)
       ```
       numerical_features = df.select_dtypes(include=['number'])
       corr = numerical_features.corr()
       sns.heatmap(corr, annot=True)
       ```
       ![{D81DCEA8-D6FD-4351-9E91-4BBCB9CC1B6B}](https://github.com/user-attachments/assets/11c0fe4c-1380-4a6e-b2a5-d409073c1ac0)
       ```
       sns.pairplot(df)
       ```
       ![{9A4A15FF-7A39-4347-AD3A-9FFA28D9D7F8}](https://github.com/user-attachments/assets/131987fc-1de1-40c7-bbc1-dc0dd3470b22)
       

# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
