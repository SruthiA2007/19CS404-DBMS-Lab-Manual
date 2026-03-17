# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="580" height="171" alt="image" src="https://github.com/user-attachments/assets/0e93fc1a-63b0-48bc-a7b6-e7a35cb66bb4" />


```sql
update sales
set sell_price=sell_price*1.05
where product_id=15 and sale_date='2023-01-31'
```

**Output:**

<img width="580" height="153" alt="image" src="https://github.com/user-attachments/assets/02bb90e0-6e99-483c-9374-b0f757be6dde" />


**Question 2**
---
<img width="444" height="233" alt="image" src="https://github.com/user-attachments/assets/4ba843a9-a557-4f11-b446-c031d2f9a268" />


```sql
select CategoryName, Description from categories
order by CategoryName
```

**Output:**

<img width="581" height="245" alt="image" src="https://github.com/user-attachments/assets/3361ddef-807f-47f6-9b34-deb7a09f83a2" />


**Question 3**
---
<img width="579" height="251" alt="image" src="https://github.com/user-attachments/assets/104dcee6-7332-414e-b155-b7283e9c5185" />


```sql
select * from employeeposition
where Salary between 50000 and 100000
```

**Output:**

<img width="583" height="137" alt="image" src="https://github.com/user-attachments/assets/639ec1c7-eab6-4631-ab18-6b1d05683086" />


**Question 4**
---
<img width="580" height="221" alt="image" src="https://github.com/user-attachments/assets/1051bb55-8297-4b35-9357-841941c6ef82" />


```sql
select id,decimal, 
case
when decimal<50 then 'Below Average'
when decimal=50 then 'Average'
else 'Above Average'
end as status
from Calculations 
```

**Output:**

<img width="569" height="270" alt="image" src="https://github.com/user-attachments/assets/7efaf04d-9d63-461d-b327-24ac0298b1b5" />


**Question 5**
---
<img width="582" height="173" alt="image" src="https://github.com/user-attachments/assets/74cf4eb6-67c3-49b9-a498-2510f2ac4113" />


```sql
select * from salesman
where city not in('Paris','Rome')
```

**Output:**

<img width="579" height="252" alt="image" src="https://github.com/user-attachments/assets/28c3682e-aa3d-4e49-9785-04fb219728c7" />


**Question 6**
---
<img width="507" height="328" alt="image" src="https://github.com/user-attachments/assets/2a403b7a-0702-436b-84a3-b79a84f661b2" />


```sql
select id,value1, ABS(value1) as absolute_value
from Calculations
```

**Output:**

<img width="561" height="207" alt="image" src="https://github.com/user-attachments/assets/647b0cf3-e055-41f2-93b3-acf48b5d1235" />


**Question 7**
---
<img width="577" height="209" alt="image" src="https://github.com/user-attachments/assets/b7d3a254-9856-4072-ac7a-eb5e6a979e15" />


```sql
delete from customer
where grade=2
```

**Output:**

<img width="429" height="320" alt="image" src="https://github.com/user-attachments/assets/f61c7296-f5ee-460a-ba6e-0d42e3373595" />


**Question 8**
---
<img width="576" height="219" alt="image" src="https://github.com/user-attachments/assets/3ecfee85-61a7-4112-bd95-8f45c7ede40c" />


```sql
delete from Doctors
where (specialization = 'Pediatrics' or specialization = 'Cardiology')
and last_name ='Brown'
```

**Output:**

<img width="575" height="397" alt="image" src="https://github.com/user-attachments/assets/1fcdc9fb-1b85-4583-a1ae-ca87e6df67fb" />


**Question 9**
---
<img width="544" height="258" alt="image" src="https://github.com/user-attachments/assets/1da7190e-4bbc-48e2-9ae8-9654462965d7" />


```sql
delete from Doctors
where doctor_id between 2 and 4
```

**Output:**

<img width="584" height="389" alt="image" src="https://github.com/user-attachments/assets/d11c3a37-5d62-402f-a67d-d3adfb089d15" />


**Question 10**
---
<img width="503" height="261" alt="image" src="https://github.com/user-attachments/assets/2f6db2a5-2cf0-4867-a57a-cd7fc609b1b1" />


```sql
delete from Surgeries
where surgery_date = '2024-02-28'=
```

**Output:**

<img width="587" height="199" alt="image" src="https://github.com/user-attachments/assets/f6a45e77-6720-40e3-acf2-e0605f14961f" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
