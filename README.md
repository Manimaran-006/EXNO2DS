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
       df=pd.read_csv("/content/titanic_dataset.csv")
       df
       ```
       ![Screenshot 2025-03-25 104957](https://github.com/user-attachments/assets/edd89df3-d98c-43d7-82df-c87ec52de8ba)

       ```
       df.info()
       ```
       ![Screenshot 2025-03-25 105036](https://github.com/user-attachments/assets/dbd0dcaf-8679-4576-ad96-c1611387312e)

       ```
       df.shape
       ```
       ![Screenshot 2025-03-25 105111](https://github.com/user-attachments/assets/c6ccb0e4-a564-484b-b9df-4999528d81cd)

       ```
       df.describe()
       ```
       ![Screenshot 2025-03-25 105147](https://github.com/user-attachments/assets/34b5f325-ba72-4263-a905-9e1a7d5a9570)

       ```
       df.nunique()
       ```
       ![Screenshot 2025-03-25 105226](https://github.com/user-attachments/assets/ce08fbd4-685d-490a-8afb-c8e159a4e1b1)

       ```
       df["Survived"].value_counts()
       ```
      ![Screenshot 2025-03-25 105304](https://github.com/user-attachments/assets/cb53fc45-b032-4ec7-920d-170413c06c52)

       ```
       per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
       per
       ```
       ![Screenshot 2025-03-25 105342](https://github.com/user-attachments/assets/059be892-6af1-4353-afd6-8a33e9754cb5)

       ```
       sns.countplot(data=df,x="Survived")
       ```
       ![Screenshot 2025-03-25 105415](https://github.com/user-attachments/assets/c403354f-329b-4c36-97eb-ea4a9b9ebdfa)

       ```
       df.Pclass.unique()
       ```
      ![Screenshot 2025-03-25 105447](https://github.com/user-attachments/assets/1f1e7299-477f-490d-906a-2d3eeef5b4d6)

       ```
       df.rename(columns={'Sex':'Gender'},inplace=True)
       df
       ```
       ![Screenshot 2025-03-25 105536](https://github.com/user-attachments/assets/68bd9e01-7b07-4638-bafe-ab788bc9dd93)

       ```
       sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
       ```
       ![Screenshot 2025-03-25 105623](https://github.com/user-attachments/assets/ff52ea70-640e-4e92-9069-62bc1a01626b)

       ```
       sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
       ```
       ![Screenshot 2025-03-25 105705](https://github.com/user-attachments/assets/5ed189a4-4064-4e77-a6db-00c605c5c45e)

       ```
       df.boxplot(column="Age",by="Survived")
       ```
       ![Screenshot 2025-03-25 105733](https://github.com/user-attachments/assets/558d8fcc-0458-408a-935e-e714cfcef97a)

       ```
       sns.scatterplot(x=df["Age"],y=df["Fare"])
       ```
       ![Screenshot 2025-03-25 105801](https://github.com/user-attachments/assets/99ef06c7-400e-4863-a0d2-7212d2327148)

       ```
       sns.jointplot(x="Age",y="Fare",data=df)
       ```
      ![Screenshot 2025-03-25 105828](https://github.com/user-attachments/assets/bba2f5ea-20ad-41f1-955e-f77879f9c1d6)

       ```
       fig, ax1 = plt.subplots(figsize=(8,5))
       plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
       ```
      ![Screenshot 2025-03-25 105913](https://github.com/user-attachments/assets/9fe20381-8845-495a-9af5-511ce271efad)

       ```
       numerical_features = df.select_dtypes(include=['number'])
       corr = numerical_features.corr()
       sns.heatmap(corr, annot=True)
       ```
      ![Screenshot 2025-03-25 105952](https://github.com/user-attachments/assets/beb85067-b97b-4029-8077-061a5a8eff4a)

       ```
       sns.pairplot(df)
       ```
      ![Screenshot 2025-03-25 110138](https://github.com/user-attachments/assets/3c017d2e-54d2-468d-b08e-0f99c0977339)

       

# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
