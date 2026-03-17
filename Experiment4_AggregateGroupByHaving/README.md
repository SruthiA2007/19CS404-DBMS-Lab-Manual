# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- <img width="577" height="385" alt="image" src="https://github.com/user-attachments/assets/7f065408-2300-451a-b259-d870108f1917" />


```python
select Medication, count(*) as TotalPrescriptions
from Prescriptions
group by Medication;
```

**Output:**

<img width="583" height="593" alt="image" src="https://github.com/user-attachments/assets/73a47a6d-c2cd-4706-a0a8-cc68da7c3f65" />


**Question 2**
---
<img width="508" height="503" alt="image" src="https://github.com/user-attachments/assets/7b14ceeb-7a0e-43c2-a21a-0ea9ce53906c" />


```sql
select strftime('%H',AppointmentDateTime) AS HourOfDay,
count(*) as TotalAppointments
from Appointments
group by HourOfDay
order by HourOfDay;
```

**Output:**

<img width="581" height="391" alt="image" src="https://github.com/user-attachments/assets/8fc7fd54-5bd0-4912-a234-b68b17c6def1" />


**Question 3**
---
<img width="579" height="377" alt="image" src="https://github.com/user-attachments/assets/6d5178a9-1bda-4e39-8a93-c7bb12edaeab" />


```sql
select InsuranceCompany, count(DISTINCT PatientID) as TotalExpiredPatients
from Insurance
where substr(ValidityPeriod, instr(ValidityPeriod,'to')+3)<'2025-10-16'
group by InsuranceCompany
order by InsuranceCompany;
```

**Output:**

<img width="470" height="413" alt="image" src="https://github.com/user-attachments/assets/27952fda-78f0-4ae5-a24d-32422bddfaf2" />


**Question 4**
---
<img width="579" height="500" alt="image" src="https://github.com/user-attachments/assets/db675bd6-ad6a-4927-9a72-cf5fa2e12691" />


```sql
select Min(purch_amt) as MINIMUM
from orders;
```

**Output:**

<img width="364" height="260" alt="image" src="https://github.com/user-attachments/assets/ac93ef9b-68ae-4684-b98f-7f203e5252f1" />


**Question 5**
---
<img width="582" height="371" alt="image" src="https://github.com/user-attachments/assets/826c6d00-5b98-41f3-aa16-5bff6d0164a5" />


```sql
select count(distinct city) as
unique_cities
from customer;
```

**Output:**

<img width="438" height="261" alt="image" src="https://github.com/user-attachments/assets/d056c680-7700-4afe-9a71-34a59044ce64" />


**Question 6**
---
<img width="460" height="397" alt="image" src="https://github.com/user-attachments/assets/2c1583df-b7df-4e8b-9d75-205223738580" />


```sql
select name, length(name) as length
from customer
order by length desc
limit 1;
```

**Output:**

<img width="578" height="259" alt="image" src="https://github.com/user-attachments/assets/911a4cc0-6f5c-4f81-8a88-75147ec20764" />


**Question 7**
---
<img width="584" height="338" alt="image" src="https://github.com/user-attachments/assets/b653838a-9b77-43a2-957d-bf0a5fae6f12" />


```sql
select avg(income) as avg_income
from employee
where name like 'A%';
```

**Output:**

<img width="340" height="257" alt="image" src="https://github.com/user-attachments/assets/ca879e08-c9d4-419e-afe5-c533f4c29ca6" />


**Question 8**
---
<img width="577" height="262" alt="image" src="https://github.com/user-attachments/assets/a3776fdc-8af8-409e-8ac5-20369d1dc52f" />


```sql
select category_id, 
sum(price*category_id) as Revenue
from products
group by category_id
having sum(price*category_id)>25;
```

**Output:**

<img width="543" height="359" alt="image" src="https://github.com/user-attachments/assets/6608fa55-521c-4dab-9adc-fa9641a13f0d" />


**Question 9**
---
<img width="585" height="243" alt="image" src="https://github.com/user-attachments/assets/ab5d602b-697c-4a70-a82e-a83ca62275b0" />


```sql
select age, min(income) as 'MIN(income)'
from employee
group by age
having income<400000;
```

**Output:**

<img width="534" height="324" alt="image" src="https://github.com/user-attachments/assets/987cf2d9-5220-4181-bd73-c6bc1c8dfdc2" />


**Question 10**
---
<img width="585" height="228" alt="image" src="https://github.com/user-attachments/assets/a5ee5a10-58fb-4c4e-9d13-4c2f4743dcb3" />


```sql
select (age/5)*5 as age_group,
AVG(age) from customer1
group by age_group 
having AVG(age)<24;
```

**Output:**

<img width="520" height="264" alt="image" src="https://github.com/user-attachments/assets/5b0ed0d0-a1b1-460b-b033-5239111ed198" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
