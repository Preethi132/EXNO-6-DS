# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 ```
  import seaborn as sns
  import matplotlib.pyplot as plt
  df = sns.load_dataset("tips")
  df
```
![image](https://github.com/user-attachments/assets/3ead595c-0c6a-4baa-807f-a4dd1e88e8da)
```
import seaborn as sns

tips = sns.load_dataset("tips")
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill.values, label='Average Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, label='Average Tip',bottom = avg_total_bill, color='orange')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
# plt.show()
```
![image](https://github.com/user-attachments/assets/b15730d3-45fc-49a3-ac08-90528c6a594f)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, label='Average Tip',bottom = avg_total_bill, color='orange', width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/10965432-8314-47f0-9b18-26cb1fa79f35)
```
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill',hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/e2ebb282-5f75-40ff-8b2b-049acb858d38)
```
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs Tip Amount')
```
![image](https://github.com/user-attachments/assets/58ec149a-470a-4271-aafa-72780f76f584)
```
import numpy as np
import pandas as pd

np.random.seed(1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name = "Num Variable")
num_var
```
![image](https://github.com/user-attachments/assets/f907e06c-5458-4444-a212-945373906475)
```
sns.histplot(data = num_var, kde=True)
```
![image](https://github.com/user-attachments/assets/7b3478e2-2571-4d49-9c26-9464d22c4cab)
```
sns.histplot(data=df, x='total_bill',hue='smoker', kde=True, palette='Set1')
plt.xlabel('Total Bill')
plt.ylabel('Frequency')
plt.title('Distribution of Total Bill by Gender')
```
![image](https://github.com/user-attachments/assets/5b55f62d-932e-427c-a8b8-fbf71d2b4273)
```
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/68b9bf61-8e4f-424f-a2ad-83511e0e6de4)
```
sns.boxplot(x='day',y='total_bill',hue='smoker',data=tips,linewidth=2,width=0.6,boxprops={'facecolor':'lightgreen','edgecolor':'blue'}, whiskerprops = {"color":"black","linestyle":"-.","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```
![image](https://github.com/user-attachments/assets/2f25fc8b-698e-4126-8212-dfbcd991ae99)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette='Set3', inner="quartile")

plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Distribution of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/019bc932-e478-4484-9f97-ed3f23e2a7e9)
```
sns.set(style="whitegrid")
tip = sns.load_dataset('tips')
sns.violinplot(x="day", y="tip", data=tip, palette='Set1')
```
![image](https://github.com/user-attachments/assets/6fb89679-9bc3-4892-b3c4-d965b7f8dac3)
```
sns.set(style="whitegrid")
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![image](https://github.com/user-attachments/assets/8665d035-a417-4a84-8b21-338d9e465612)
```
sns.set(style="whitegrid")
tip = sns.load_dataset('tips')
sns.violinplot(x="tip", y="day", data=tip, palette='plasma')
```
![image](https://github.com/user-attachments/assets/0c7930ff-7d8f-4e61-a03c-71bb5d4d45bf)
```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/58802b04-dcc9-48a7-8afa-02d7c53e66f7)
```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/5e648a6e-dde9-4fa9-b089-2edc328d1d46)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
print("The data to be plotted:\n")
print(data)
```
![image](https://github.com/user-attachments/assets/1a1f7f64-cfcd-4444-8c68-2e1033cd8714)
```
hm = sns.heatmap(data = data, annot=True)
```
![image](https://github.com/user-attachments/assets/281e901c-3e42-4174-b9d8-4a50df9376db)
```
tips = sns.load_dataset('tips')
numeric_cols = tips.select_dtypes(include=np.number)
corr = numeric_cols.corr()
```
![image](https://github.com/user-attachments/assets/fc132521-b28c-4017-a130-78b53ea0bafb)


# Result:
  We have performed Data Visualization using seaborn python library for the given datas.
