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
df=pd.read_csv("C:\\Users\\admin\\Downloads\\titanic_dataset.csv")
df
```

<img width="1356" height="462" alt="image" src="https://github.com/user-attachments/assets/16895397-4ea5-45f4-8886-50dd53e328ff" />

```
df.info()

```
<img width="677" height="418" alt="image" src="https://github.com/user-attachments/assets/b086e088-e7c8-4f40-beac-8cb14e8f8811" />

```
df.describe()

```
<img width="798" height="336" alt="image" src="https://github.com/user-attachments/assets/d0ff31f9-a45f-408b-8861-2c42bd84de3e" />

```
df.dtypes

```
<img width="478" height="295" alt="image" src="https://github.com/user-attachments/assets/b21c2f1c-65b2-4497-9d74-797e8f14521c" />

```
df.value_counts()

```
<img width="1302" height="533" alt="image" src="https://github.com/user-attachments/assets/a3e4895c-8000-4b41-8a2a-80a50520116b" />

```
df['Age'].value_counts()

```
<img width="486" height="282" alt="image" src="https://github.com/user-attachments/assets/044536d5-1b41-4090-8b13-54cf7b2fed80" />

```
df.set_index("PassengerId",inplace=True)
df.describe()

```
<img width="767" height="312" alt="image" src="https://github.com/user-attachments/assets/671d29ed-f3bc-484e-88ba-b6f9a347525a" />

```
df.shape
```

<img width="223" height="53" alt="image" src="https://github.com/user-attachments/assets/e0d58f7d-7e0b-4cde-a489-e2267c140741" />

```
df.nunique()
```

<img width="457" height="270" alt="image" src="https://github.com/user-attachments/assets/da39ffc6-82b2-4822-8495-4a30e3d2b420" />

```
sns.countplot(data=df,x='Survived')
```

<img width="808" height="575" alt="image" src="https://github.com/user-attachments/assets/54641a7b-7dd2-4544-babf-7e655fb7e18c" />

```
df.Pclass.unique()
```

<img width="407" height="48" alt="image" src="https://github.com/user-attachments/assets/3f8b1693-ea38-4d98-99e7-ebec0bd5a230" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1241" height="450" alt="image" src="https://github.com/user-attachments/assets/490cf518-e373-4116-9a4c-4699e5a89036" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)
```

<img width="969" height="689" alt="image" src="https://github.com/user-attachments/assets/5103f857-d4d4-4645-bbbd-01c06fd01c6d" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="785" height="621" alt="image" src="https://github.com/user-attachments/assets/37de9cd5-57f3-4c27-878d-c4dc5c154f4a" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="812" height="601" alt="image" src="https://github.com/user-attachments/assets/8ffdceae-daf6-4905-b2cb-d2bc80abde51" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="973" height="562" alt="image" src="https://github.com/user-attachments/assets/35f99b5d-fb93-4d28-860f-129c4a175165" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="796" height="540" alt="image" src="https://github.com/user-attachments/assets/d036db4a-e3d8-475b-8401-0191b1fc3138" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1052" height="490" alt="image" src="https://github.com/user-attachments/assets/90531383-13f5-4812-9c91-81a3d2d0fff3" />

```
sns.pairplot(data=df)
```

<img width="1476" height="1476" alt="image" src="https://github.com/user-attachments/assets/d4b8c7d2-166c-4bbe-a66a-282a7f3104b6" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1, annot=True)
```

<img width="713" height="575" alt="image" src="https://github.com/user-attachments/assets/c11f359e-6524-4546-90f6-9a2ed8436a5a" />

# RESULT
Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.

