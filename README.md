# Exno:1
Data Cleaning Process
# Name: VIMALA SAHANA W
# Reg No: 212223040241
# Date: 12-03-2025

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
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![Screenshot 2025-03-12 180956](https://github.com/user-attachments/assets/ffa57819-a59f-44a6-8036-3ff422679c55)

```
df.head()
```
![Screenshot 2025-03-12 181159](https://github.com/user-attachments/assets/4046e1dc-6b6d-4ade-add4-a3514bd0f0b3)

```
df.tail()
```
![Screenshot 2025-03-12 181252](https://github.com/user-attachments/assets/e4d6f9c3-7018-403f-8ff4-e2126b61174a)

```
df.isnull()
```
![Screenshot 2025-03-12 181405](https://github.com/user-attachments/assets/435aa7cc-bdb9-48d4-b9ed-b398e1654331)

```
df.fillna(600)
```
![Screenshot 2025-03-12 181501](https://github.com/user-attachments/assets/6365887b-1758-4dc5-8040-b8d5e1a6f209)

```
df.dropna(axis=1)
```
![Screenshot 2025-03-12 181554](https://github.com/user-attachments/assets/180b3162-f074-4223-baec-9427977ae35b)

```
df.dropna(axis=0)
```
![Screenshot 2025-03-12 181644](https://github.com/user-attachments/assets/060b313d-8d8e-49a9-af40-9b866fee4ce9)

```
df.isnull().sum()
```
![Screenshot 2025-03-12 181731](https://github.com/user-attachments/assets/4f05770b-3145-4b08-9551-e7e79aec6333)

```
df.isnull().any()
```
![Screenshot 2025-03-12 181953](https://github.com/user-attachments/assets/ca7e5a82-6951-418a-8856-c6a6f7fd0cb7)

```
df.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/e6286500-a141-4e58-a9da-8853cfed0e89)

```
df.fillna(method='bfill')
```
![Screenshot 2025-03-12 182136](https://github.com/user-attachments/assets/2113fdc9-2a28-41db-844e-1eb48f10ef80)

```
df.fillna({'GENDER':'FEMALE','NAME':'ILLAI','ADDRESS':'CHENNAI','M1':'85','M2':'89','M3':'90'})
```
![Screenshot 2025-03-12 182251](https://github.com/user-attachments/assets/0d324aa3-ffd0-459b-9dab-ae28a36f7ab0)

```
df.info()
```
![Screenshot 2025-03-12 182335](https://github.com/user-attachments/assets/3a0da2db-20f0-43c0-9cb1-de863853d925)

```
df.describe()
```
![Screenshot 2025-03-12 182415](https://github.com/user-attachments/assets/922fa567-735e-4bd9-a877-c8f8d6d2e8c5)

```
df.shape
```
![Screenshot 2025-03-12 182456](https://github.com/user-attachments/assets/8085a65a-8c9c-465d-95c2-91175eef689d)

```
ir=pd.read_csv("/content/iris.csv")
ir
```
![Screenshot 2025-03-12 182534](https://github.com/user-attachments/assets/c427347b-e34c-4af4-bbc6-06865769a2d2)

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![Screenshot 2025-03-12 182741](https://github.com/user-attachments/assets/46772362-edb1-438d-83e5-4ff8ab094137)

```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
IQR=Q3-Q1
print(IQR)
```
![Screenshot 2025-03-12 182830](https://github.com/user-attachments/assets/7d152e4f-4a62-45cd-9708-e6df510f31da)

```
rid=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
rid['sepal_width']
```
![Screenshot 2025-03-12 182910](https://github.com/user-attachments/assets/6c498dc9-8f20-4b69-9967-67fff851adb3)

```
delid=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
delid
```
![Screenshot 2025-03-12 183030](https://github.com/user-attachments/assets/2d5e6ce3-2648-4148-b228-2d61b0bf0cb2)

```
sns.boxplot(x='sepal_width',data=delid)
```
![Screenshot 2025-03-12 183114](https://github.com/user-attachments/assets/e504cd51-af01-4a70-a939-0447c5a57b91)

```
import scipy.stats as stats
import numpy as np
z=np.abs(stats.zscore(ir['sepal_width']))
z
```
![Screenshot 2025-03-12 183219](https://github.com/user-attachments/assets/69ca0c3a-0dbb-4e8c-8f9a-22404b663fba)

```
df1=ir[z<0.8]
df1
```
![Screenshot 2025-03-12 183304](https://github.com/user-attachments/assets/0b9afdbe-7d6d-480a-8b5a-f9816597b276)







































# Result

Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
          
