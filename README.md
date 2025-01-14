# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE

Name: Yogeshvar M            
Reg : 212222230180
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset('tips')

# Drop rows with all missing values
tips.dropna(how='all', inplace=True)
sns.barplot(x='day', y='total_bill', data=tips)
plt.show()

# a) Which day of the week has the highest total bill amount?

# Group by day and sum total_bill
total_bill_by_day = tips.groupby('day')['total_bill'].sum()

# Sort by descending order and select the first row
highest_total_bill_day = total_bill_by_day.sort_values(ascending=False).index[0]

print("The day with the highest total bill amount is:", highest_total_bill_day)

# b) What is the average tip amount given by smokers and non-smokers?

sns.barplot(x='smoker', y='tip', data=tips)
plt.show()

# Group by smoker and calculate mean of tip
tip_by_smoker = tips.groupby('smoker')['tip'].mean()

print("Average tip amount given by smokers:", tip_by_smoker['Yes'])
print("Average tip amount given by non-smokers:", tip_by_smoker['No'])

# c) How does the tip percentage vary based on the size of the dining party?

tips['tip_percentage'] = tips['tip'] / tips['total_bill'] * 100
sns.pointplot(x='size', y='tip_percentage', data=tips)
plt.show()

# Create a new column for tip percentage
tips['tip_percentage'] = tips['tip'] / tips['total_bill']

# Group by size and calculate mean of tip percentage
tip_percentage_by_size = tips.groupby('size')['tip_percentage'].mean()

print("Tip percentage by size of dining party:")
print(tip_percentage_by_size)

# d) Which gender tends to leave higher tips?

sns.boxplot(x='sex', y='tip', data=tips)
plt.show()

# Group by gender and calculate mean of tip
tip_by_gender = tips.groupby('sex')['tip'].mean()

print("Average tip amount by gender:")
print(tip_by_gender)

# e) Is there any relationship between the total bill amount and the day of the week?

sns.scatterplot(x='total_bill', y='day', data=tips)
plt.show()

# f) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?

sns.boxplot(x='time', y='total_bill', data=tips)
plt.show()

# g) Which dining party size group tends to have the highest average total bill amount?

sns.barplot(x='size', y='total_bill', data=tips)
plt.show()

# Group by size and calculate mean of total_bill
total_bill_by_size = tips.groupby('size')['total_bill'].mean()

print("Average total bill amount by size of dining party:")
print(total_bill_by_size)

# h) What is the distribution of tip amounts for each day of the week?

sns.boxplot(x='day', y='tip', data=tips)
plt.show()

# i) How does the tip amount vary based on the type of service (lunch vs. dinner)?

sns.boxplot(x='time', y='tip', data=tips)
plt.show()

# j) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x='total_bill', y='tip', data=tips)
plt.show()
correlation = tips['total_bill'].corr(tips['tip'])
print("Correlation coefficient between total_bill and tip:", correlation)
```

# OUPUT
![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/5ce4ff1e-938a-43df-8a7a-bb6b96578481)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/526da315-de62-491a-98e3-4d2a6fa84485)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/7f97c862-26a5-4e6f-98b2-81f4ed81e26e)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/2bd2d86a-92d4-46e2-acc0-754aef8b5e9f)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/223efccb-28e6-4028-ad4c-1ccd0b83c4fb)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/178bf211-ff98-4751-b51a-04e0602dfd72)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/731c05c7-74ce-4da1-af47-948e88d1de84)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/3ee284c1-e823-450c-bdc4-ac5a333323b5)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/c5273041-f0b1-4b11-b0c3-2a49c875d319)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/bec3799b-0a64-4f20-979a-1997a5019597)

![image](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-09/assets/113497367/4987d602-9def-4dc8-bb3f-a097ae4fd7bf)


# RESULT
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.
