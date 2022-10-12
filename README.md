AIM

To read the given data and perform Feature Generation process and save the data to a file.

Explanation

Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

ALGORITHM

STEP 1

Read the given Data

STEP 2

Clean the Data Set using Data Cleaning Process

STEP 3

Apply Feature Generation techniques to all the feature of the data set

STEP 4

Save the data to the file


Coding:

import pandas as pd

df=pd.read_csv("/content/data[1].csv")

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sns.set(style ="darkgrid")

sns.countplot(df['Ord_2'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)

![image](https://user-images.githubusercontent.com/113016781/195274771-f243fd66-f15c-4217-a521-2a3866599d50.png)

![image](https://user-images.githubusercontent.com/113016781/195274889-d53a6b77-cf96-4a64-8901-00e285362cb9.png)

![image](https://user-images.githubusercontent.com/113016781/195275013-9c3a3113-75ec-42bb-a0ac-1d28323a2dde.png)

![image](https://user-images.githubusercontent.com/113016781/195275097-6b9217cf-0166-47b7-baf6-12aafc0f5e5e.png)

![image](https://user-images.githubusercontent.com/113016781/195275153-3600b303-ed4a-4930-8324-b58fe7eebb93.png)

Encoding data

![image](https://user-images.githubusercontent.com/113016781/195281215-19053f9b-4d17-4789-89ac-194414912906.png)

![image](https://user-images.githubusercontent.com/113016781/195281471-1f555304-05cd-4397-bad8-f2e2996416c5.png)

![image](https://user-images.githubusercontent.com/113016781/195281632-49ecdb51-2cf0-45ee-b5d5-1aadbb7cd685.png)

![image](https://user-images.githubusercontent.com/113016781/195281717-4efa41e7-332a-41ec-bf11-43a6871bd21c.png)

titanic data 

import pandas as pd

df=pd.read_csv("/content/titanic_dataset.csv")

df.info()

df.isnull().sum()

![image](https://user-images.githubusercontent.com/113016781/195308210-baa85472-1b64-4225-b12e-1b889c7ff89c.png)

df['Age']=df['Age'].fillna(df['Age'].mean())

df['Cabin']=df['Cabin'].fillna(df['Cabin'].mode()[0])

df['Embarked']=df['Embarked'].fillna(df['Embarked'].mode()[0])

df.isnull().sum()

![image](https://user-images.githubusercontent.com/113016781/195308334-78c097fa-4b18-4a5f-90d2-c2f44fa44e80.png)

from sklearn. preprocessing import LabelEncoder

le = LabelEncoder()

df ['Sex'] = le.fit_transform(df['Sex' ])

sns . set(style ="darkgrid")

sns . countplot (df [ 'Sex' ])

![image](https://user-images.githubusercontent.com/113016781/195308531-1b4e12b3-bf7a-44ff-9d16-c96ee949247b.png)

from sklearn. preprocessing import OneHotEncoder

enc = OneHotEncoder ( )

enc = enc. fit_transform(df [ [ 'Name' ]]) . toarray()

encoded_colm = pd. DataFrame(enc)

df = pd. concat([df, encoded_colm], axis=1)

df = df . drop(['Name' ], axis=1)

df . head(10)

![image](https://user-images.githubusercontent.com/113016781/195308653-80430cab-8372-46f1-b842-6373c487ef8f.png)

df = pd.get_dummies (df, prefix=['Ticket'], columns=[ 'Ticket'])

df . head ( 10 )

![image](https://user-images.githubusercontent.com/113016781/195308747-0a3f9246-3cfa-4770-a92d-6189517ef854.png)

df = pd.get_dummies (df, prefix=['Embarked'], columns=[ 'Embarked'])

df . head ( 10 )

![image](https://user-images.githubusercontent.com/113016781/195308885-cd32215d-5586-4b2b-855c-f34efae228a4.png)

df= pd.get_dummies(df, prefix=['Cabin'], columns=[ 'Cabin' ])

df . head (10)

![image](https://user-images.githubusercontent.com/113016781/195308964-fc3124d5-7f23-41f6-a5b8-94da450b35c4.png)

Result:

   Feature Generation process and save the data to a file are performed










