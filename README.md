# Feature_Encoding_Scaling
# Ex:05 Feature Generation
# AIM
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
STEP 1
Read the given Data

STEP 2
Clean the Data Set using Data Cleaning Process

STEP 3
Apply Feature Generation techniques to all the feature of the data set

STEP 4
Save the data to the file

# PROGRAM
```
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```
# Data.csv
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df1.head()
df1['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
df1['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
# BMI.csv file
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```
# OUTPUT
For encoding.csv file
Initial data:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/87f0e2ba-5cd8-456f-b5a7-ef6132de8605)

Unique value:

![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/e8914047-71b5-40e8-8c91-dad6845bd606)


Ordinal Encoder:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/76c8b6dd-4dbb-4811-bffb-567a60b64eed)


Label Encoder:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/d5a46487-cd39-437e-af46-225fd7bfdea0)


Binary Encoder:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/39555802-8835-442e-ad23-41e9cefda8d2)


![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/ddb17a5b-525c-4f84-b236-36c4902e1d49)


For Data.csv file
Initial data:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/030181e9-0ec5-4100-ac42-3dbd0d90ec85)


Unique data:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/504b014a-13a9-4572-b88b-8e1a7be39071)


Ordinal Encoder:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/11b758b0-604d-42e4-8e5d-81b2081e69e6)


![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/1e5099d7-ea01-4032-aa92-c1877a4761c1)


Label Encoder:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/cc8ff56e-5d88-4066-b854-0503d9e48214)


Binary Encoder:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/5decba62-e96c-45b9-9088-ce0ff31f05b9)


![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/81cef44a-eece-4304-b5b2-e429f6e6f584)


For bmi.csv file
Initial data:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/1b15dc02-5df5-4e55-b122-ec949823de36)


Binary Encoders:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/023e2aa8-dbc9-41dc-8f8e-7620af781e0e)


Dummies:
![image](https://github.com/vishnupriya20052004/DataScience_exp5/assets/133640291/71132541-3b18-48ae-a02e-6a45c6c03eaa)


# RESULT:
The Feature Generation process was performed and saved the data to a file.
