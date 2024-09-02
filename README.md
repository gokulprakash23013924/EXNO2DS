EXNO2DS

AIM:
To perform Exploratory Data Analysis on the given data set.

EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

CODING AND OUTPUT
import pandas as pd import numpy as np import matplotlib.pyplot as plt import seaborn as sns df=pd.read_csv("/content/titanic_dataset.csv") df

Screenshot 2024-08-27 114351

df.info()

Screenshot 2024-08-27 114646

df.shape

Screenshot 2024-08-27 114800

df.describe()

Screenshot 2024-08-27 115008

df.set_index("PassengerId",inplace=True) df.describe()

Screenshot 2024-08-27 115422

df.nunique()

Screenshot 2024-08-27 115501

df["Survived"].value_counts()

Screenshot 2024-08-29 103410

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) per

Screenshot 2024-08-27 115706

sns.countplot(data=df,x="Survived")

Screenshot 2024-08-27 115751

df.Pclass.unique()

Screenshot 2024-08-27 115838

df.rename(columns= {'Sex':'Gender'}, inplace=True) df

Screenshot 2024-08-27 115923

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

Screenshot 2024-08-27 120140

sns.catplot(x='Survived',hue="Gender",data=df,kind="count")

Screenshot 2024-08-27 120221

df.boxplot(column="Age",by="Survived")

Screenshot 2024-08-27 120308

sns.scatterplot(x=df["Age"],y=df["Fare"])

Screenshot 2024-08-27 120348

sns.jointplot(x="Age",y="Fare",data=df)

Screenshot 2024-08-27 120439

fig,ax1 = plt.subplots(figsize=(8,5)) pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

Screenshot 2024-08-27 120542

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="Count")

Screenshot 2024-08-29 104329

corr = df.corr() sns.heatmap(corr,annot=True)

Screenshot 2024-08-29 104337

sns.pairplot(df)

Screenshot 2024-08-27 120655

RESULT
Hence performing Exploratory Data Analysis on the given data set is successful
