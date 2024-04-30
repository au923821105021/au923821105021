import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
     
In [3]:

# Load the dataset
data = pd.read_csv("/content/E-commerce Website Logs.csv")
     
In [4]:

# Display basic information about the dataset
print("Dataset shape:", data.shape)
     
Dataset shape: (97752, 15)
In [5]:

print("\nColumns:", data.columns)
     
Columns: Index(['accessed_date', 'duration_(secs)', 'network_protocol', 'ip', 'bytes',
       'accessed_Ffom', 'age', 'gender', 'country', 'membership', 'language',
       'sales', 'returned', 'returned_amount', 'pay_method'],
      dtype='object')
In [6]:
print("\nData types:\n", data.dtypes)
     
Data types:
 accessed_date        object
duration_(secs)     float64
network_protocol     object
ip                   object
bytes               float64
accessed_Ffom        object
age                  object
gender               object
country              object
membership           object
language             object
sales               float64
returned             object
returned_amount     float64
pay_method           object
dtype: object
# Plot visualizations

# Distribution of sales
plt.figure(figsize=(10, 6))
sns.histplot(data['sales'], bins=20, kde=True)
plt.title('Distribution of Sales')
plt.xlabel('Sales')
plt.ylabel('Frequency')
plt.show()
      
# Sales vs. Age 
 plt.figure(figsize=(10, 6))
sns.scatterplot(x='age', y='sales', data=data)
plt.title('Sales vs. Age')
plt.xlabel('Age')
plt.ylabel('Sales')
plt.show()
     

 
# Sales by Country
plt.figure(figsize=(12, 8))
sns.boxplot(x='country', y='sales', data=data)
plt.title('Sales by Country')
plt.xlabel('Country')
plt.ylabel('Sales')
plt.xticks(rotation=45)
plt.show()


# Sales by Language
plt.figure(figsize=(12, 8))
sns.boxplot(x='language', y='sales', data=data)
plt.title('Sales by Language')
plt.xlabel('Language')
plt.ylabel('Sales')
plt.xticks(rotation=45)
plt.show()
     
 


