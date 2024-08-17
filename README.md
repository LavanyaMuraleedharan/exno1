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

## Data cleaning process
```
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
```
![image](https://github.com/user-attachments/assets/2299188a-8659-45f8-85fb-eb5f91e609e9)

```
df.head()
```
![image](https://github.com/user-attachments/assets/210619b6-82bb-40d7-bf5e-aa26c63295a8)

```
df.tail()
```
![image](https://github.com/user-attachments/assets/22cc09e7-f9ee-4beb-98c4-4721fe3826a9)

```
df.isnull()
```
![image](https://github.com/user-attachments/assets/27ee30a7-6856-49e6-b2fb-cadf9ef30de9)

```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/0594e09c-018b-4590-b71f-286e64575fd8)

```
df.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/7e6db8e7-4c49-468b-88af-345c14b1a231)

```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/83da199d-69f9-444e-8f14-63ce518800e1)

```
print(df.shape)
```
![image](https://github.com/user-attachments/assets/1a29f35f-98d7-46ee-ac1d-a95f17e95525)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/d3535d8b-d4b6-47ac-86fb-2efc4bf1608f)


## IQR

```
import pandas as pd
import seaborn as sns
ir=pd.read_csv('/content/iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/eeaf6f67-12fb-4527-a812-8d168593cf7c)

```
ir.describe()
```
![image](https://github.com/user-attachments/assets/cbd1bd2a-7457-48b4-8ee3-0cf1c1288d9a)

```
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/f761b6c1-61bc-4729-a764-4b02c6188b55)

```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![image](https://github.com/user-attachments/assets/3e6d5368-69f7-4a72-a5de-849bce34b1c0)

```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/48821a98-7f84-4f27-894e-85f21fa5e2ad)

```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/aab08ed1-dc5e-4200-a3b5-c34ad4451029)

```
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/f7861390-f4d1-4fad-86b1-6fa54e3e8af3)

## Z SQUARE

```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset
```
![image](https://github.com/user-attachments/assets/3e2e33c3-21ac-4f2d-af39-8cf467c42a9f)

```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/e47bf9b7-f54c-49d6-8708-064a370ac080)

```
low = q1 - 1.5*iqr
low
```
![image](https://github.com/user-attachments/assets/e857bec7-99cd-4929-a46d-9baba634eed2)

```
high = q3 + 1.5*iqr
high
```
![image](https://github.com/user-attachments/assets/b3eab148-fe33-4d2a-8f10-b5c2159fb50e)

```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![image](https://github.com/user-attachments/assets/3f72c2f3-4f99-4dae-a9ac-9e065ee05fd1)

```
z = np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/user-attachments/assets/aa950c7e-2f00-44ff-b45a-5263388d2d14)

```
df1 = df[z<3]
df1
```
![image](https://github.com/user-attachments/assets/7c32bcea-ed19-436c-836f-51add2f0f875)


# Result
Thus the Data Cleaning Process and Detecting and Removal of Outliers is executed successfully.
