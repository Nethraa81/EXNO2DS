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

## CODING AND OUTPUT:

```
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv('titanic_dataset.csv')
df
```
<img width="1586" height="617" alt="image" src="https://github.com/user-attachments/assets/79828113-58fe-4795-aab6-c3c939cd619b" />

```
df.info()
```
<img width="511" height="485" alt="image" src="https://github.com/user-attachments/assets/8cbd3744-d955-4052-b031-74683936ff78" />

```
df.describe()
```
<img width="920" height="416" alt="image" src="https://github.com/user-attachments/assets/74b2fbca-0530-4081-a948-c5a536e1b3cb" />

```
df.dtypes
```
<img width="277" height="351" alt="image" src="https://github.com/user-attachments/assets/5d1960b4-5da9-4ecd-ac9e-1045a1326320" />

```
df.shape
```
<img width="411" height="45" alt="image" src="https://github.com/user-attachments/assets/a9bb9a45-7235-45f8-a2b1-6747dcfbec85" />

```
df['Age'].value_counts()
```
<img width="436" height="343" alt="Screenshot 2025-09-13 154509" src="https://github.com/user-attachments/assets/7d608606-2bb1-424f-8045-4c36ec822c3b" />

```
df.set_index("PassengerId")
df
```
<img width="1601" height="614" alt="Screenshot 2025-09-13 154729" src="https://github.com/user-attachments/assets/5d599c5a-c6e0-4414-a6fc-1d6836aa1dc8" />

```
df.nunique()
```
<img width="263" height="345" alt="image" src="https://github.com/user-attachments/assets/8639cc6b-1e02-4af6-919f-097b1907afdb" />

```
sns.countplot(data=df,x='Survived')
```
<img width="983" height="691" alt="image" src="https://github.com/user-attachments/assets/a84025d6-a84c-4157-b7b9-ae9442d24491" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1587" height="605" alt="image" src="https://github.com/user-attachments/assets/0ecfa8c1-5e3f-4f87-b0ba-12cb57be0b51" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="1142" height="715" alt="image" src="https://github.com/user-attachments/assets/49981d2e-8fe2-45ae-ab04-fb0a1a053e9a" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="855" height="658" alt="image" src="https://github.com/user-attachments/assets/e8decb18-fd14-457e-8011-a87915a090a8" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="815" height="620" alt="image" src="https://github.com/user-attachments/assets/1e372099-d9e7-483e-a4d1-322c1b45c0ca" />

```
plt=sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)
```
<img width="800" height="592" alt="image" src="https://github.com/user-attachments/assets/44bb437a-b16e-4b5b-8b73-8fc9ee444706" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1445" height="687" alt="image" src="https://github.com/user-attachments/assets/a29d51b3-6e57-4cd3-b55e-46afb5f85209" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="855" height="707" alt="image" src="https://github.com/user-attachments/assets/05951c7b-b69a-43a4-82a8-8c8cf178e6dc" />

# RESULT
Hence the program to perform Exploratory Data Analysis on the given data set has been done successfully.
