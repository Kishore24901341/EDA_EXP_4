# EDA_EXP_4   Titanic Survival Analysis using Univariate Analysis

# KISHORE V
# 212224240077

# Aim

To perform univariate analysis on the Titanic dataset to understand the distribution and characteristics of individual variables (such as Age, Sex, Pclass, Fare, and Survived) and to draw insights about passengers and their survival patterns.


# Algorithm

**1)Import Libraries:**

Load the required Python libraries (pandas, numpy, matplotlib, seaborn).

**2)Load the Dataset:**

Read the Titanic dataset from available sources (e.g., seaborn’s built-in Titanic dataset or a CSV file).

**3)Data Inspection:**

View the first few rows using head().

Get dataset summary using info() and describe().

**4)Handle Missing Data:**
Identify missing values using isnull().sum() and handle them appropriately (e.g., fill or drop).

**5)Univariate Analysis:**
Perform univariate analysis for each variable:

**Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)**
Use frequency tables and count plots.

**Numerical Variables: (e.g., Age, Fare)**
Use histograms, box plots, and summary statistics.

**6)Interpretation:**
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


# Program

A. Data Understanding
Load the Titanic dataset and display the first 5 records.
What is the shape of the dataset (rows, columns)?
Identify which columns have missing values.
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

print("Name: KISHORE V" )
print("Reg No: 212224240077")

df = sns.load_dataset('titanic')

print("\nFirst 5 Records:")
print(df.head())

print("\nShape of Dataset (rows, columns):", df.shape)

print("\nMissing Values in Each Column:")
print(df.isnull().sum())
```
B. Categorical Variable Analysis

What is the distribution of the sex variable?
```
print("\nDistribution of Sex:")
print(df['sex'].value_counts())
```
What percentage of passengers survived (survived column)?
```
survival_rate = df['survived'].mean() * 100
print(f"\nPercentage of Passengers Survived: {survival_rate:.2f}%")
```
Which passenger class (pclass) had the maximum passengers?
```
print("\nPassenger Count by Class:")
print(df['pclass'].value_counts())
```
How many passengers embarked from each port (embarked)?
```
print("\nEmbarked Distribution:")
print(df['embarked'].value_counts())
```
Which deck had the most passengers?
```
print("\nDeck Distribution:")
print(df['deck'].value_counts())
```

C. Numerical Variable Analysis

Plot the distribution of passenger age. What is its mean, median, and range?
```
print("\nAge Statistics:")
print("Mean Age:", df['age'].mean())
print("Median Age:", df['age'].median())
print("Minimum Age:", df['age'].min())
print("Maximum Age:", df['age'].max())
print("Range:", df['age'].max() - df['age'].min())

plt.hist(df['age'].dropna(), bins=30)
plt.title("Age Distribution")
plt.xlabel("Age")
plt.ylabel("Frequency")
plt.show()
```

Plot a boxplot for fare and comment on the presence of outliers.
```
plt.boxplot(df['fare'].dropna())
plt.title("Fare Boxplot")
plt.show()
```

What does the shape of the fare histogram indicate about fare distribution?
```
plt.hist(df['fare'], bins=30)
plt.title("Fare Distribution")
plt.xlabel("Fare")
plt.ylabel("Frequency")
plt.show()
```

Compare mean and median for fare – what can you infer about skewness?
```
print("Mean Fare:", df['fare'].mean())
print("Median Fare:", df['fare'].median())
```

# Output

A. Data Understanding
<img width="723" height="769" alt="image" src="https://github.com/user-attachments/assets/fd61b10f-556e-40e0-ba84-eb197be538db" />


B. Categorical Variable Analysis
<img width="954" height="661" alt="Screenshot 2026-02-13 113709" src="https://github.com/user-attachments/assets/ce167896-4dd9-41f9-bb6e-c67e39aa0c61" />

C. Numerical Variable Analysis

Plot the distribution of passenger age. What is its mean, median, and range?
<img width="950" height="684" alt="Screenshot 2026-02-13 113749" src="https://github.com/user-attachments/assets/ce8d9937-9afc-4d38-9886-1d231d0d17a6" />

Plot a boxplot for fare and comment on the presence of outliers.
<img width="951" height="436" alt="Screenshot 2026-02-13 113804" src="https://github.com/user-attachments/assets/0bffb686-fd90-45cb-a579-7126e7e699ba" />

What does the shape of the fare histogram indicate about fare distribution?
<img width="953" height="472" alt="Screenshot 2026-02-13 113818" src="https://github.com/user-attachments/assets/74b82a6c-91b9-4adc-a48c-ca08ec80931b" />

Compare mean and median for fare – what can you infer about skewness?
<img width="958" height="109" alt="Screenshot 2026-02-13 113834" src="https://github.com/user-attachments/assets/01ef7db6-fd4c-4f67-a8c0-b652704e8462" />

D. Insights

1. From your analysis, what kind of passengers were most common?

Answer:
The dataset shows that most passengers were male. A large proportion of travelers belonged to third class (Pclass = 3). The majority of passengers boarded the ship at Southampton (S). In terms of age distribution, young adults represented the largest group of passengers.

2. What initial trends can you observe that may relate to survival?

Answer:
From the preliminary observations, several patterns appear to influence survival. Female passengers had a noticeably higher survival rate than males. Passengers traveling in first class had better chances of survival compared to those in lower classes. Individuals who paid higher fares were more likely to survive. Additionally, children tended to have a higher survival rate compared to many adults.

3. Why is univariate analysis an important first step in data analysis?

Answer:
Univariate analysis is essential because it focuses on examining each variable separately to understand its characteristics. It helps identify the distribution, central tendency (mean and median), variability, missing values, and possible outliers in the data. By performing this step first, analysts can detect errors, understand patterns, and prepare the dataset properly, which improves the accuracy of later analyses such as correlation studies or predictive modeling. It serves as the foundation for effective data analysis.


# Result
From the univariate analysis:
Majority of passengers were male and in 3rd class.
Around 38% survived, majority being females and higher-class passengers.
Age is right-skewed with most passengers aged 20–40 years.
Fare distribution shows a few high outliers for 1st class passengers.
Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.
