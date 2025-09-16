# EXNO2DS
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
import seaborn as sns
df=pd.read_csv("/titanic_dataset.csv")
df
```
<img width="842" height="532" alt="image" src="https://github.com/user-attachments/assets/e4c9aa74-fc48-472a-93e0-63e4f6d191f4" />

```
df.info()
```
<img width="328" height="316" alt="image" src="https://github.com/user-attachments/assets/545681d9-e9c6-4ec7-a91d-8f1febb7e7de" />

```
df.describe()
```
<img width="611" height="296" alt="image" src="https://github.com/user-attachments/assets/00b7407e-e1f6-4513-9ab0-b74b0f8d09fd" />

```
df.dtypes
```
<img width="162" height="303" alt="image" src="https://github.com/user-attachments/assets/f4e646c0-d68f-4d21-aff2-7f2a09cb9a34" />

```
df.shape
```
<img width="133" height="47" alt="image" src="https://github.com/user-attachments/assets/77842095-aa28-4647-91de-312c690c6c9a" />

```
df.value_counts()
```
<img width="773" height="295" alt="image" src="https://github.com/user-attachments/assets/0ea50214-371d-45e4-8104-856a54182398" />

```
df['Age'].value_counts()
```
<img width="176" height="312" alt="image" src="https://github.com/user-attachments/assets/e188b091-ca99-4262-86be-3ac5f9518010" />

```
df.set_index("PassengerId",inplace=True)
df
```
<img width="698" height="306" alt="image" src="https://github.com/user-attachments/assets/87560269-317c-4d14-98b0-71b2ac09ed3d" />

```
df.nunique()
```
<img width="161" height="281" alt="image" src="https://github.com/user-attachments/assets/ac38a2be-e090-496e-b6e8-c53ec9d48a52" />

```
sns.countplot(data=df,x="Age")
```
<img width="431" height="307" alt="image" src="https://github.com/user-attachments/assets/9174e52d-cc84-4f62-832e-bf71c2a2f858" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="703" height="311" alt="image" src="https://github.com/user-attachments/assets/ca3d63d2-5eaf-4a67-b36a-7bbbf69fbf0e" />

```
sns.catplot(x="Age",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="523" height="340" alt="image" src="https://github.com/user-attachments/assets/fe84c861-c683-48ab-a4bf-ec393ca82b71" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="417" height="322" alt="image" src="https://github.com/user-attachments/assets/6090302e-6c5a-46a4-8051-c670119b1abc" />

```
sns.scatterplot(x=df["Age"],y=df['Fare'])
```
<img width="435" height="306" alt="image" src="https://github.com/user-attachments/assets/7d52f2e4-ffd8-4fb9-a965-a453dc4ead19" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="431" height="292" alt="image" src="https://github.com/user-attachments/assets/d17c0918-588e-49b3-9048-10ef812b5bd2" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```
<img width="718" height="336" alt="image" src="https://github.com/user-attachments/assets/245f4b78-2ed0-4547-9d8a-23eaf9ef16e0" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="411" height="302" alt="image" src="https://github.com/user-attachments/assets/ce49982e-74a0-40da-8095-b0c3943557dd" />


# RESULT
Thus, Exploratory Data Analysis on the given data set is successfully performed.
