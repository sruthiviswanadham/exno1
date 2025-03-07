# NAME:V.V.SAI SRUTHI
# REG NO:212223100061

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
df
```
![image](https://github.com/user-attachments/assets/5a613312-011b-43e4-b3d0-b35239c06a89)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/bdcf017e-46af-40c9-a6c3-757024b0506c)
```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/cd913a2d-9ef7-488a-a041-2494b5c528dd)
```
df.dropna()
```
![image](https://github.com/user-attachments/assets/e83e6ac3-a1de-4d20-bf05-19faf79bd126)
```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/b1397d05-f31a-4ca4-b285-d3de26d9a2fa)
```
df.info()
```
![image](https://github.com/user-attachments/assets/38356b85-e88f-4296-8837-6f842dfb04d9)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/3646ae5a-22f4-4668-aea9-0899fc473a24)
```
df.fillna(method = 'ffill')
```
![image](https://github.com/user-attachments/assets/9e5228eb-4d8f-49c7-a1dc-51803c1e9579)
```
df.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/9ab21693-5427-4c2d-9f02-4143f5bd7b3d)
```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALLE','M1':'90','M2':'35','M3':'97','M4':'67'})
```
![image](https://github.com/user-attachments/assets/32f814e6-4a5f-40ae-b82c-2e04b09bf1ff)
```
df=pd.read_csv("iris.csv")
df
```
![image](https://github.com/user-attachments/assets/ddf34e70-2b59-4eec-8ed9-d56bdab59bb8)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/801477b3-57c5-4125-a100-6e24b5d46bcc)
```
df.info()
```
![image](https://github.com/user-attachments/assets/b0a65f57-6a6f-4566-bfc5-5583777d723c)
```
df.shape
```
![image](https://github.com/user-attachments/assets/7523fc87-ccd1-43b7-bff6-49e702cd29ad)
```
import matplotlib.pyplot as plt
import seaborn as sns
sns.boxplot(x='sepal_width',data=df)
```
![image](https://github.com/user-attachments/assets/00698db9-38c7-44e9-8707-927469aee093)
```
sns.boxplot(x='sepal_length',data=df)
```
![image](https://github.com/user-attachments/assets/5bef3d73-0890-4381-995f-e401edf8361d)
```
from ctypes import c_int16
q1=df.sepal_width.quantile(0.25)
q3=df.sepal_width.quantile(0.75)
iq=q3-q1
print(q3)
```
![image](https://github.com/user-attachments/assets/2236eccb-2a4e-46e9-8564-e43e9e0fea4c)
```
rid=df[(df.sepal_width<(q1-1.5*iq))|(df.sepal_width>(q3+1.5*iq))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/17fcbcdc-bcb9-48c7-896d-e34448117102)
```
delid=df[~((df.sepal_width<(q1-1.5*iq))|(df.sepal_width>(q3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/44d9ea76-55fb-42b4-8e18-e368b40e085e)
```
import pandas as pd
import numpy as np
import scipy.stats as stats
df=pd.read_csv("heights.csv")
df
```
![image](https://github.com/user-attachments/assets/3c46afb7-7028-4b84-a6d3-fe8e83f2d596)
```
z=np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/user-attachments/assets/38079bf8-2eea-41ec-bc20-177ff9404dbd)
```
df1=df[z<3]
df1
```
![image](https://github.com/user-attachments/assets/ecb59b02-2164-4efe-aa40-cee78b3ce957)




# Result
          
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
