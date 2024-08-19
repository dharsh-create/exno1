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
df=pd.read_csv("/content/SAMPLEIDS (1).csv")
df
```
![image](https://github.com/user-attachments/assets/edb31204-c80d-4cf4-aeeb-7777a6808a11)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/26c8e67f-eb27-48c8-82c6-ddfb1dd75f6a)
```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/3da87db9-2977-4d26-93ba-59a238d97b05)
```
df.dropna()
```
![image](https://github.com/user-attachments/assets/7bb95ef9-8679-4458-b685-dc9a94112e47)
```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/798dc2ff-828e-4861-9fb6-fe10faf5e863)
```
df.fillna(method = 'ffill')
```
![image](https://github.com/user-attachments/assets/8d350b8c-a52f-4705-9473-026d87f9c133)
```
df.fillna(method = 'bfill')
```
![image](https://github.com/user-attachments/assets/7a7ad8ec-fb1b-47f2-8c80-af4b6cfa7ca8)
```
df_dropped = df.dropna()
df_dropped
```
![image](https://github.com/user-attachments/assets/69d15ad8-98fc-487e-a6d8-87bb55ac3fbf)
```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![image](https://github.com/user-attachments/assets/87e1f136-b4e8-45c9-909c-422bfdfbeb65)
```
IQR(Inter Quartile Range)
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/f11df85f-8a62-4756-aa00-3b2713f70d22)
```
ir.describe()
```
![image](https://github.com/user-attachments/assets/d31cf25c-5451-4c28-ab42-1de0ad645128)
```
import seaborn as sna
sna.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/cdd87efd-8957-4118-9132-b7720793d272)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/5cb6db50-c57f-435c-b96d-48c21fab388f)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/27b2f7a4-b6ce-469e-8029-8457e7bda253)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/a06daefb-729a-4872-8e4e-552738dc3ccd)
```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset
```
![image](https://github.com/user-attachments/assets/9ad183d8-1b3b-4932-8589-7fcb22037a7a)
```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/2c9e2703-4801-48f2-b72c-21a53cd81bce)
```
low = q1 - 1.5*iqr
low
```
![image](https://github.com/user-attachments/assets/4e0c5240-b0cf-4acd-a05b-10ee2e8e8260)
```
high = q3 + 1.5*iqr
high
```
![image](https://github.com/user-attachments/assets/27ff369f-494b-4ab5-b004-51cbd3ddfe80)
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![image](https://github.com/user-attachments/assets/71058370-3159-460e-b982-932622da8adc)
```
z = np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/user-attachments/assets/59cb1d75-785a-4038-b048-af3e938a5f71)
```
df1 = df[z<3]
df1
```
![image](https://github.com/user-attachments/assets/4f79c9ac-44f5-414d-a188-cd96b95218d7)
```






























                       











                    
# Result
          <<include your Result here>>
