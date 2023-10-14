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

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/a6ea4d5f-9b71-4de1-a2b9-bb0f8f0c40fd)


Unique value:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/89712a8c-ffb6-4256-855b-3480f48a11a3)


Ordinal Encoder:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/161ea8da-ec58-49e3-a818-75bd073a231f)


Label Encoder:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/7387df68-7e08-45ed-baf0-8cb3f9414ce5)

Binary Encoder:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/a4249cbe-ea79-491f-b28b-954d03e94194)


![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/8d28a4c7-f03f-45a6-8b8b-c1f34a6f9263)

For Data.csv file
Initial data:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/7d052dd7-3859-41da-ae10-aebbe1617308)


Unique data:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/9f3d05b0-61da-419a-b658-771e8312c625)


Ordinal Encoder:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/02a426ce-526f-451b-afc1-d94c7c5554bf)

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/d2464011-f212-43ad-9a21-3042b911c821)


Label Encoder:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/7302e4fd-69bd-409a-9bc3-a966cc8a3df2)


Binary Encoder:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/0d626b19-f144-4ea5-9ff4-77583abc2aed)



![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/2184fde1-bd48-489d-8ec6-707d81ac654d)



For bmi.csv file
Initial data:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/b2a4aec1-de8e-41e1-a876-9a4d3d5f281b)



Binary Encoders:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/146e3a03-de86-4722-aece-bfd3fc2edf24)


Dummies:

![image](https://github.com/Anuayshh/DSExpt5/assets/127651217/145f84a5-5691-4e14-ac88-028c25c78e06)



# RESULT:
The Feature Generation process was performed and saved the data to a file.
