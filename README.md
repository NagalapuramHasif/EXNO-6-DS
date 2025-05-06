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
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/197f9cf5-98b0-40c9-8233-e6aa5915d7e8)

```
df=sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/eb2adf0d-17d1-404f-80ed-f27811955bb4)

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")
```
![image](https://github.com/user-attachments/assets/939460d4-7e6f-4581-b062-b0e7957c5bd3)

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title('Multi-Line Plot')
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
![image](https://github.com/user-attachments/assets/ccfb9572-42fc-4cf0-a808-532539777639)

```
import seaborn as sns
import matplotlib.pyplot as plt
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/928c7af0-4c30-448c-9643-593709c4a9b8)

```
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/bbf3eb79-2cd8-4baa-9412-eb341585f480)

```
years=range(2000,2012)
apples=[0.895,0.91,0.919,0.926,0.929,0.931,0.934,0.936,0.937,0.9375,0.9372,0.939]
oranges=[0.962,0.941,0.930,0.923,0.918,0.908,0.907,0.904,0.901,0.898,0.9,0.896]
import seaborn as sns
dt=sns.load_dataset("tips")
sns.barplot(x='day',y='total_bill',hue='sex',data=dt,palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Average Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/ab7b2bd2-61d0-49e0-97ad-5f162a9502ae)

```
import pandas as pd
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/482dd989-5be2-47d5-a594-ce4add60de40)

```
plt.figure(figsize=(8,6))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/df058191-064e-4ad0-aac8-cc9bb1a1af54)

```
import seaborn as sns
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=tips)
plt.xlabel("Total Bill")
plt.ylabel("Tip Amount")
plt.title("Scatter Plot of Total Bill vs. Tip Amount")
```
![image](https://github.com/user-attachments/assets/31b5b240-2360-4f99-8f0b-c49189cfb730)

```
import seaborn as sns
import numpy as np
import pandas as pd
np.random.seed(1)
num_var=np.random.randn(1000)
num_var=pd.Series(num_var,name="Numerical Variable")
num_var
```
![image](https://github.com/user-attachments/assets/711383e0-0fba-4b45-9dd8-2737a67bdcb5)

```
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/9dbcb4d7-d75e-463b-a38a-fc772cd39798)

```
import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks
```
![image](https://github.com/user-attachments/assets/e344237a-adb5-49e7-a834-f9b6a1a07773)

```
sns.histplot(data=marks,bins=10,kde=True,stat='count',cumulative=False,multiple='stack',element='bars',palette='Set1',shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of student Marks')
```
![image](https://github.com/user-attachments/assets/e4ef352f-ae5d-405b-a10c-6947a280fbb3)

```
import seaborn as sns
import pandas as pd
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/990175cb-8b3c-45ec-9cdb-1bb84adfb343)

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,boxprops={"facecolor":"lightblue","edgecolor":"darkblue"},
            whiskerprops={"color":"black","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```
![image](https://github.com/user-attachments/assets/7f7ed980-0a14-41b0-a036-e1673e619998)

```
sns.boxplot(x='Pclass',y='Age',data=df,palette='rainbow')
plt.title("age by Passenger Class,Titanic")
```
![image](https://github.com/user-attachments/assets/353860d9-76e3-4cd8-99d0-7f9a04d50cba)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips,linewidth=2,width=0.6,
palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/696a5edb-6ea2-4a2a-bbbe-6afc29d5f683)

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
mart=pd.read_csv("/content/supermarket.csv")
mart
```
![image](https://github.com/user-attachments/assets/82eb7230-93c1-4206-b3aa-a5bfe8227422)

```
mart=mart[['Gender', 'Payment', 'Unit price', 'Quantity', 'Total', 'gross income']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/dd9e229b-97ea-47f0-8fad-05f8711e6799)

```
sns.kdeplot(data=mart,x='Total')
```
![image](https://github.com/user-attachments/assets/f9153ea3-c0b7-4894-af1f-c373b86f5dbf)

```
sns.kdeplot(data=mart,x='Unit price')
```
![image](https://github.com/user-attachments/assets/39ceb981-f95f-46e3-b9a9-041a8d17f464)

```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/c4dffd41-7f52-4269-b9a0-a0f05ed2c57f)

```
sns.kdeplot(data=mart,x='Total', hue='Payment', multiple='stack')
```
![image](https://github.com/user-attachments/assets/2fd59c4e-6304-410b-8284-103429720010)

```
sns.kdeplot(data=mart, x='Total', hue='Payment', multiple='stack',linewidth=5,palette="Dark2", alpha=0.5)
```
![image](https://github.com/user-attachments/assets/9f2b49cf-ef5f-4dc5-a29f-90ade62501c2)

```
sns.kdeplot(data=mart, x='Unit price',y='gross income')
```
![image](https://github.com/user-attachments/assets/12c2e5ee-b918-49c0-9c65-f005ce464034)

```
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted.\n")
print(data)
```
![image](https://github.com/user-attachments/assets/34558da9-57a5-43d8-b99b-db7e1e32f104)

```
data=np.random.randint(low=1,high=100,size=(10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/66758719-4860-43e3-a7fd-163ce7f6725d)

```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/77cd4d7b-6b0d-4bda-8394-35da4f3e43f6)

# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
