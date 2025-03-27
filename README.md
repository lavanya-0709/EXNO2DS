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

## CODING AND OUTPUT
# Name: LAVANYA S
# Reg. no: 212223230112
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
dataset = pd.read_csv("/content/titanic_dataset.csv")
dataset
```
![image](https://github.com/user-attachments/assets/a70c0e29-b0eb-4e43-b3dd-e90e16d29a00)
```
dataset.info()
```
![image](https://github.com/user-attachments/assets/0c33be09-2dcd-4e4f-a4b6-94d848396871)
```
dataset.shape
```
![image](https://github.com/user-attachments/assets/240a948b-6920-4982-9757-c31c90fb01cb)
```
dataset.set_index("PassengerId",inplace=True)
dataset.describe()
```
![image](https://github.com/user-attachments/assets/a920d0e3-adfa-43e0-a48e-6b56675a5bfe)
```
dataset.shape
```
![image](https://github.com/user-attachments/assets/f0cbab29-492b-460d-a481-cc058ac9fc89)
# Categorical data analysis
```
dataset.nunique()
```
![image](https://github.com/user-attachments/assets/16ef097b-1ba2-45bd-be84-c628543c39a3)
```
dataset["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/eed26966-2c4e-4c36-82ad-db581702ac0a)
```
var=(dataset["Survived"].value_counts()/dataset.shape[0]*100).round(2)
var
```
![image](https://github.com/user-attachments/assets/e1f04630-73eb-4e27-b95f-b192fb864f20)
```
sns.countplot(data=dataset,x="Survived")
```
![image](https://github.com/user-attachments/assets/f89cbb91-33c0-4610-aa07-804a3bda733c)
```
dataset
```
![image](https://github.com/user-attachments/assets/4ceeea56-26c0-4e82-8274-476b253dfbcd)
```
dataset.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/8029ec35-e18f-4a1f-a3f6-31a9ef131a84)
```
dataset.rename(columns={'Sex':'Gender'},inplace=True)
dataset
```
![image](https://github.com/user-attachments/assets/6acf7ffc-fa49-4a5e-8dc4-62912cf59047)
#  Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dataset,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/4902a078-e693-4520-a2da-a18267bc38bc)
```
sns.catplot(x="Survived",hue="Gender",data=dataset,kind="count")
```
![image](https://github.com/user-attachments/assets/a75ff6db-4227-4152-becf-81104bfb08d4)
```
dataset.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/a27fa432-4b20-4fca-a30d-111e7858f10c)
```
sns.scatterplot(x=dataset["Age"],y=dataset["Fare"])
```
![image](https://github.com/user-attachments/assets/5d2aca6b-84db-4bf2-9f72-63efbea99fad)
```
sns.jointplot(x="Age",y="Fare",data=dataset)
```
![image](https://github.com/user-attachments/assets/e2ca2ab0-d3c7-4613-87aa-766753da2171)
# Multivariate Analysis
```
fig = plt.figure(figsize=(8, 5))  # Create a figure with the desired size
ax1 = fig.add_subplot(1, 1, 1)  # Add a subplot to the figure
sns.boxplot(ax=ax1, x='Pclass', y='Age', hue='Gender', data=dataset)
plt.show()  # Display the plot
```
![image](https://github.com/user-attachments/assets/a23875c9-fc29-43d1-8dab-5c697bc2f8b5)
```
sns.catplot(data=dataset,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/f6f6af71-b830-461e-a385-dde132e65437)
#  Co-relation
```
numeric_features = dataset.select_dtypes(include=np.number)
corr = numeric_features.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/37ef2714-3194-46e9-97c7-5b35895f192c)
```
sns.pairplot(dataset)
```
![image](https://github.com/user-attachments/assets/80576fa5-68ae-4785-af65-584ec97bf479)


# RESULT
 We have performed Exploratory Data Analysis on the given data set successfully
