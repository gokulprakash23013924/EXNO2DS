 EXNO2DS
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

import pandas as pd 
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("/content/titanic_dataset.csv")
df

![Screenshot 2024-08-27 114351](https://github.com/user-attachments/assets/7e5e17a3-0ca7-465f-b728-d3c67a2a4f7d)



df.info()


![Screenshot 2024-08-27 114646](https://github.com/user-attachments/assets/d603f787-94f1-4138-819d-418a86f5ddea)


df.shape

![Screenshot 2024-08-27 114800](https://github.com/user-attachments/assets/4e2ffc5f-d198-4f87-bf17-e75162558d79)


df.describe()

![Screenshot 2024-08-27 115008](https://github.com/user-attachments/assets/bc6d662d-2259-4ca7-b3bf-a0c3e612cd4b)



df.set_index("PassengerId",inplace=True)
df.describe()

![Screenshot 2024-08-27 115422](https://github.com/user-attachments/assets/f1cb5106-e322-4800-a8ca-87f242eeb6ac)


df.nunique()

![Screenshot 2024-08-27 115501](https://github.com/user-attachments/assets/16756e99-833c-412a-ba62-39defb8408b6)


df["Survived"].value_counts()

![Screenshot 2024-08-29 103410](https://github.com/user-attachments/assets/f8cd1730-ac50-4e4b-8299-df5e2d4cbc84)



per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) 
per

![Screenshot 2024-08-27 115706](https://github.com/user-attachments/assets/ca17452e-4508-4d6e-a724-a4c79a8a4152)


sns.countplot(data=df,x="Survived")

![Screenshot 2024-08-27 115751](https://github.com/user-attachments/assets/6edb9293-3408-432a-aff6-29073117693b)


df.Pclass.unique()

![Screenshot 2024-08-27 115838](https://github.com/user-attachments/assets/b5fae832-3ca6-4bc9-9b38-c25ba29f4503)




df.rename(columns= {'Sex':'Gender'}, inplace=True)
df

![Screenshot 2024-08-27 115923](https://github.com/user-attachments/assets/45c69834-ef85-4b91-9a98-af73278edd81)


sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

![Screenshot 2024-08-27 120140](https://github.com/user-attachments/assets/1f4e823f-312e-4a23-baa4-4372015fe9da)


sns.catplot(x='Survived',hue="Gender",data=df,kind="count")

![Screenshot 2024-08-27 120221](https://github.com/user-attachments/assets/d5c1e2c6-7932-40a9-8ed6-36b86738b0bd)


df.boxplot(column="Age",by="Survived")

![Screenshot 2024-08-27 120308](https://github.com/user-attachments/assets/9ef48650-fc8d-4d2b-9705-6fd2c5dac1f7)



sns.scatterplot(x=df["Age"],y=df["Fare"])


![Screenshot 2024-08-27 120348](https://github.com/user-attachments/assets/7a11bb7d-5ee8-402a-92c6-0753d8e5ac27)



sns.jointplot(x="Age",y="Fare",data=df)


![Screenshot 2024-08-27 120439](https://github.com/user-attachments/assets/a280a685-5f5d-4842-b53b-62042d0df77b)


fig,ax1 = plt.subplots(figsize=(8,5)) 
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)


![Screenshot 2024-08-27 120542](https://github.com/user-attachments/assets/b1f4d0ae-9300-427a-8f7f-753d61661708)


sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="Count")

![Screenshot 2024-08-29 104329](https://github.com/user-attachments/assets/dc5ae73b-a7a5-45a2-a1dc-7e4f0f0bfb52)


corr = df.corr()
sns.heatmap(corr,annot=True)

![Screenshot 2024-08-29 104337](https://github.com/user-attachments/assets/1444abfb-ca59-4081-9842-698369d1670b)



sns.pairplot(df)

![Screenshot 2024-08-27 120655](https://github.com/user-attachments/assets/8478ee30-f907-483b-8772-2693e57ada6e)



# RESULT
Hence performing Exploratory Data Analysis on the given data set is successful
