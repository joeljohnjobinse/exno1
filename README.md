# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
ds
```
![image](https://github.com/user-attachments/assets/d0626cf3-9144-487b-bedf-a92b1a10ffa0)

```
df.info()
```
![image](https://github.com/user-attachments/assets/584420b9-bb81-4d0e-b7cf-4ea305989745)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/c40bcdeb-2958-4760-aeef-be6acf92cd7a)

```
df.head(3)
```
![image](https://github.com/user-attachments/assets/5a54d045-c8e4-420f-a8a8-dd2621fc3adc)

```
df.tail(3)
```
![image](https://github.com/user-attachments/assets/2da35913-0b96-4c5b-adc3-79fa1b3c3cd3)

```
df['DOB'] = pd.to_datetime(df['DOB'],errors='coerce',format=None)
df.shape
```

![image](https://github.com/user-attachments/assets/73bff61f-5e82-414a-92a8-9ef2b13e2262)

```
df.isnull().sum()
```

![image](https://github.com/user-attachments/assets/d017035e-fcc2-44b2-96b4-f3f9e7b06a66)

```
df.nunique()
```

![image](https://github.com/user-attachments/assets/43c1674b-53fb-4294-82ee-2f8f2b843a3a)

```
df['GENDER'].value_counts()
```

![image](https://github.com/user-attachments/assets/be5fbd8f-8d11-4415-9beb-d1624bd4b906)

```
df.dropna(how='any').shape
```

![image](https://github.com/user-attachments/assets/0d11e4dc-2b28-4bc7-b993-8d86fe564e93)

```
x=df.dropna(how='any')
x
```
![image](https://github.com/user-attachments/assets/68ade944-2af4-4fc1-9c1c-0f165d86bab2)

```
df.dropna(how='all').shape
```

![image](https://github.com/user-attachments/assets/7ef04cc7-c7d5-4a58-94eb-e86c83f79401)

```
tot=df.dropna(subset=['TOTAL'],how='any')
tot
```

![image](https://github.com/user-attachments/assets/781e1cf5-ae25-4b66-9ca8-69f985787caa)

```
tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')
tot
```

![image](https://github.com/user-attachments/assets/f1c68253-50fa-4baa-8e4b-f27b079464c0)

```
s=df.fillna(0)
s
```

![image](https://github.com/user-attachments/assets/74caba7f-b7a0-4391-9d3d-7bc551695f3c)

```
s=df.fillna(method='ffill')
s
```

![image](https://github.com/user-attachments/assets/59a1f94a-d7a0-456b-bc4d-0bfc3ebfe682)

```
s=df.fillna(method='bfill')
s
```

![image](https://github.com/user-attachments/assets/cf08ee9d-2516-4233-9911-e34bf4ed8953)

```
df.isna().sum()
```

![image](https://github.com/user-attachments/assets/590ff868-1095-4e4e-b2b6-ebb9aeacc7a1)

```
df['M1']
```

![image](https://github.com/user-attachments/assets/ace99a78-0a6f-4dd8-b24c-19ccb45720b4)

```
df.isnull()
```

![image](https://github.com/user-attachments/assets/0c29e62e-6aa4-42f9-badf-7359e91b8637)

```
df.notnull()
```

![image](https://github.com/user-attachments/assets/4a741b30-c62e-4d80-8f80-aeb0ec3d52c0)

```
x1=df.dropna(axis=0)
x1
```

![image](https://github.com/user-attachments/assets/1a1e0147-2d02-4c9c-bf6b-e8aeba2c051f)

```
df.duplicated()
```

![image](https://github.com/user-attachments/assets/17919906-b439-473f-9623-44ac8f05679a)

```
m=df.drop_duplicates(inplace=False)
m
```

![image](https://github.com/user-attachments/assets/d76be688-4b8f-416e-95a4-4db77ec6d81d)

```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```

![image](https://github.com/user-attachments/assets/e2634801-329a-4d37-b9ac-45bd632d6dd1)

```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```

![image](https://github.com/user-attachments/assets/bb73a58a-c571-45f9-b67f-c23eaaec30a7)

```
print(df.loc[0:3])
```

![image](https://github.com/user-attachments/assets/0032b935-135d-4452-ade4-fd3e30bffcc0)

```
df.dtypes
```

![image](https://github.com/user-attachments/assets/14117f9d-d813-42c7-9e4d-5d4ad00286d5)

```
df.iloc[[1,3,5],[1,3]]
```

![image](https://github.com/user-attachments/assets/13d5d284-aa85-47e8-8aad-46275ecbdb27)

# Result
Thus we have cleaned the data and removed the outliers by detection using IQR
