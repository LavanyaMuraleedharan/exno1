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



# Result
          <<include your Result here>>
