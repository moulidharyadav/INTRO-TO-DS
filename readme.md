# 19AI403 ASSIGNMENT-LAB INTRODUCTION
### Prepared By : K SANTHAN KUMAR
### Register Number : 212223240065
### DEPT : AIML 2nd YEAR

## Requirements :

- Python 3.x
- Pandas library


## Data :

The data used for this assignment is from `bank_train.csv`, which includes various columns related to client information and their interactions with the bank.

## CODE :

## Activity 1

This section covers the tasks in Activity 1, which involve selecting specific columns and filtering rows based on certain conditions from a DataFrame.

### Task 1: Select the 'name' and 'score' columns from a given DataFrame

```python
import pandas as pd
import numpy as np

# Sample DataFrame
exam_data = {
    'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],
    'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
    'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1]
}

df_exam = pd.DataFrame(exam_data)

# Selecting 'name' and 'score' columns
name_score_df = df_exam[['name', 'score']]
print(name_score_df)
```

**Output:**
![image](https://github.com/user-attachments/assets/aab22217-f307-46cf-9c72-ddfd093d8391)


### Task 2: Select the rows where the 'attempts' column is greater than 3

```python
attempts_gt_3 = df_exam[df_exam['attempts'] > 3]
print(attempts_gt_3)
```

**Output:**

![image](https://github.com/user-attachments/assets/a10dd689-c514-4ecb-b1c9-7b4922244fbd)


### Task 3: Index rows and columns based on specific conditions

Given DataFrame:

```python
data = {
    'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
    'age': [25, 35, 40, 28],
    'gender': ['F', 'M', 'M', 'M'],
    'salary': [50000, 70000, 60000, 80000]
}
df = pd.DataFrame(data)
```

#### a. Select rows where age is greater than 30:

```python
age_gt_30 = df[df['age'] > 30]
print(age_gt_30)
```

**Output:**

![image](https://github.com/user-attachments/assets/b691822a-c83e-42ed-b589-45e67f46b7e9)


#### b. Select rows where name contains 'e':

```python
name_contains_e = df[df['name'].str.contains('e')]
print(name_contains_e)
```

**Output:**

![image](https://github.com/user-attachments/assets/869d50bd-6337-4f70-abea-5ed62bcddda6)


#### c. Select rows where gender is 'M' and salary is greater than 65000:

```python
male_high_salary = df[(df['gender'] == 'M') & (df['salary'] > 65000)]
print(male_high_salary)
```

**Output:**

![image](https://github.com/user-attachments/assets/823e20a2-bbd9-4043-a4ee-eb577035e351)


#### d. Select columns 'name' and 'age':

```python
name_age_df = df[['name', 'age']]
print(name_age_df)
```

**Output:**

![image](https://github.com/user-attachments/assets/b7ac52dc-6cb8-4156-908b-a1f10381d368)

## Activity 2

This section covers the tasks in Activity 2, which involve filtering and selecting specific rows and columns from the `bank_train.csv` dataset.

### Task a

**Condition:** Select the rows where clients with primary education have subscribed to a deposit.

```python
primary_education_subscribed = df_bank.loc[(df_bank['education'] == 'primary') & (df_bank['deposit'] == 'yes')]
print(primary_education_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/738bf407-2257-4873-ba08-da475a3c1b3a)


### Task b

**Condition:** Select the rows where clients have not subscribed to a deposit.

```python
not_subscribed = df_bank.loc[df_bank['deposit'] == 'no']
print(not_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/4e3b6c66-51c0-4165-93bd-bc75c4a0dd56)

### Task c

**Condition:** Select the rows where clients who have subscribed to a deposit either have a housing or a personal loan.

```python
subscribed_with_loans = df_bank.loc[(df_bank['deposit'] == 'yes') & ((df_bank['housing'] == 'yes') | (df_bank['loan'] == 'yes'))]
print(subscribed_with_loans)
```

**Output:**

![image](https://github.com/user-attachments/assets/6b067710-29a4-46c9-87a7-b11094ca2ff1)


### Task d

**Condition:** Select the rows where clients with secondary education who have not subscribed to a deposit.

```python
secondary_not_subscribed = df_bank.loc[(df_bank['education'] == 'secondary') & (df_bank['deposit'] == 'no')]
print(secondary_not_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/c9584cfd-157a-48f8-9432-d67b359e155d)


### Task e

**Condition:** Select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign.

```python
subscribed_success = df_bank.loc[(df_bank['deposit'] == 'yes') & (df_bank['poutcome

'] == 'success')]
print(subscribed_success)
```

**Output:**

![image](https://github.com/user-attachments/assets/9220b116-bdf3-45c6-be0d-36d76a14336e)


### Task f

**Condition:** Select the rows where unemployed clients have not subscribed to a deposit.

```python
unemployed_not_subscribed = df_bank.loc[(df_bank['job'] == 'unemployed') & (df_bank['deposit'] == 'no')]
print(unemployed_not_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/b58b2fe2-88f0-41a3-bda0-13963d9e8dc2)

### Task g

**Condition:** Select columns 'name' and 'salary' where age is less than or equal to 30. (Note: Adjust 'name' and 'salary' to the actual column names.)

```python
young_clients = df_bank.loc[df_bank['age'] <= 30, ['job', 'balance']]
print(young_clients)
```

**Output:**

![image](https://github.com/user-attachments/assets/2fd69b3b-8eb1-4403-a2d9-9b005ee2a006)


## Results

The results above demonstrate how to filter and select data using Pandas' `loc` method based on specific conditions. This can be useful in analyzing marketing data and understanding client behavior.

---
