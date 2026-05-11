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
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```

<img width="1242" height="427" alt="image" src="https://github.com/user-attachments/assets/b1f7605b-b871-4e25-9cd7-6066fab83612" />

```
df.info()
```

<img width="421" height="413" alt="image" src="https://github.com/user-attachments/assets/dd42d3bb-8ed9-42ea-8e48-6bfe9471faf7" />

```
df.describe()
```

<img width="762" height="298" alt="image" src="https://github.com/user-attachments/assets/9bc0bc69-0326-4cab-b469-b8fc9b9c8a3f" />

```
df.dtypes
```

<img width="271" height="281" alt="image" src="https://github.com/user-attachments/assets/92d48488-283c-44f8-a29b-2b2ee1c449de" />

```
df.value_counts()
```


<img width="1247" height="537" alt="image" src="https://github.com/user-attachments/assets/69e8a959-1400-48de-acdf-3338e3860c81" />

```
df['Age'].value_counts()
```

<img width="416" height="278" alt="image" src="https://github.com/user-attachments/assets/b2086096-0762-45c0-9661-964754afe908" />

```

df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="638" height="312" alt="image" src="https://github.com/user-attachments/assets/60c86c90-549a-46a8-832c-60bcf2c566c3" />

```
df.shape
```

<img width="327" height="35" alt="image" src="https://github.com/user-attachments/assets/116b77c9-b614-4873-84ed-3a94948db1a4" />

```
df.nunique()
```

<img width="312" height="268" alt="image" src="https://github.com/user-attachments/assets/1d00d9e5-d76a-4b9d-88d8-5d5aad6371ea" />

```
sns.countplot(data=df,x='Survived')
```

<img width="840" height="582" alt="image" src="https://github.com/user-attachments/assets/0c1f30cf-b8eb-46e7-a6ef-c8c7a3b47d32" />

```
df.Pclass.unique()
```

<img width="382" height="33" alt="image" src="https://github.com/user-attachments/assets/cba65984-be06-45b5-b81b-6b5574df3494" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1230" height="468" alt="image" src="https://github.com/user-attachments/assets/98e727b0-5306-4757-9ce3-b06b92fc1bda" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)
```

<img width="1115" height="806" alt="image" src="https://github.com/user-attachments/assets/4dab833e-ba6b-4c04-9174-6c188ad35208" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="682" height="557" alt="image" src="https://github.com/user-attachments/assets/c42a8872-703b-4570-ba61-1439ea03c85d" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="716" height="517" alt="image" src="https://github.com/user-attachments/assets/77c47095-8f9b-49de-bf4d-415d29e15f35" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="833" height="518" alt="image" src="https://github.com/user-attachments/assets/6b9a02ff-bd98-446f-a98c-8b58edf071f4" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="697" height="488" alt="image" src="https://github.com/user-attachments/assets/c4077aa0-40c1-4724-b313-40fc1e675d02" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1103" height="553" alt="image" src="https://github.com/user-attachments/assets/8d4f1163-9081-429a-a88c-2f6688cfb840" />

```
sns.pairplot(data=df)
```

<img width="830" height="848" alt="image" src="https://github.com/user-attachments/assets/67c15090-7a8c-4ec6-aaea-7d1527facc62" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1, annot=True)
```

<img width="540" height="446" alt="image" src="https://github.com/user-attachments/assets/5419527e-37ac-4370-9086-43634f030324" />

# RESULT
        
      Thus we have clened the data and removed the outliers by detection using IQR and Z-score method.
