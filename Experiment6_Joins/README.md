# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="582" height="314" alt="image" src="https://github.com/user-attachments/assets/6ac4f486-3925-494b-b6fd-0b8dd7f24fa1" />


```sql
select cust_name, ord_no, ord_date, purch_amt
from customer as c
left join orders as o
on c.customer_id=o.customer_id;
```

**Output:**

<img width="580" height="365" alt="image" src="https://github.com/user-attachments/assets/56bbaec6-e562-41f0-8e3f-5e07a6853d81" />


**Question 2**
---
<img width="576" height="783" alt="image" src="https://github.com/user-attachments/assets/36ab7f93-c9c0-4383-967f-7c5c0e6bcb5e" />


```sql
SELECT
  c.cust_name,
  c.city,
  o.ord_no,
  o.ord_date,
  o.purch_amt AS "Order Amount",
  s.name,
  s.commission
FROM
  customer c
LEFT JOIN
  orders o ON c.customer_id = o.customer_id
LEFT JOIN
  salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="582" height="368" alt="image" src="https://github.com/user-attachments/assets/f1a927b9-6b92-4c3f-9be0-a36996a40d7b" />
<img width="576" height="424" alt="image" src="https://github.com/user-attachments/assets/834507d7-9359-4d9b-a684-c64357cafca8" />



**Question 3**
---
<img width="581" height="343" alt="image" src="https://github.com/user-attachments/assets/956036d8-7d21-48e4-a8b8-4ccd5dca136d" />


```sql
select p.date_of_birth,a.appointment_id, p.patient_id, p.doctor_id, a.appointment_date
from patients as p
inner join appointments as a
on p.patient_id=a.patient_id
where first_name like "%Alice";
```

**Output:**

0<img width="583" height="193" alt="image" src="https://github.com/user-attachments/assets/c01fc719-725e-48ee-ae71-a1e2483b6b4f" />


**Question 4**
---
<img width="583" height="435" alt="image" src="https://github.com/user-attachments/assets/ad870f06-562c-488b-8205-188b4b6f4a2b" />


```sql
select o.ord_no,o.ord_date,o.purch_amt,
c.cust_name as "Customer Name",
c.grade,
s.name as "Salesman",
s.commission
from orders as o
inner join customer as c
on o.customer_id=c.customer_id
inner join salesman as s
on o.salesman_id = s.salesman_id;
```

**Output:**

<img width="583" height="367" alt="image" src="https://github.com/user-attachments/assets/2560c5eb-d417-4ccf-b18f-744c2bc4c0ef" />
<img width="576" height="447" alt="image" src="https://github.com/user-attachments/assets/996b36d6-8a9a-4793-896d-2823c5b93495" />


**Question 5**
---
<img width="584" height="238" alt="image" src="https://github.com/user-attachments/assets/7bb802ac-2d37-4790-b577-47d3d85f36b5" />


```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';
```

**Output:**

<img width="578" height="368" alt="image" src="https://github.com/user-attachments/assets/4bbea0da-e04e-4185-8ed0-9840f7c5a84f" />

**Question 6**
---
<img width="584" height="424" alt="image" src="https://github.com/user-attachments/assets/d9304a32-12fb-4e71-a538-be685d4d728b" />


```sql
SELECT c.cust_name AS "Customer Name",
       c.city,
       s.name AS "Salesman",
       s.city,
       s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;
```

**Output:**

<img width="583" height="257" alt="image" src="https://github.com/user-attachments/assets/95d5a5a2-ff74-433a-b29a-acd9387a0c74" />


**Question 7**
---
<img width="583" height="354" alt="image" src="https://github.com/user-attachments/assets/555a6074-3fc3-4a6f-b650-e0ba1be6cd29" />


```sql
select p.first_name as "patient_name", a.appointment_id, a.patient_id, a.doctor_id, a.appointment_date
from patients as p
inner join appointments as a
on p.patient_id=a.patient_id;
```

**Output:**

<img width="587" height="231" alt="image" src="https://github.com/user-attachments/assets/a4853103-b7f3-4605-988e-ce29daec8696" />


**Question 8**
---
<img width="580" height="373" alt="image" src="https://github.com/user-attachments/assets/332c8e40-c27d-4e3f-8fc2-df85c0e9a863" />


```sql
SELECT p.first_name, s.*
FROM patients p
INNER JOIN surgeries s ON p.patient_id = s.patient_id
WHERE p.discharge_date BETWEEN '2024-03-01' AND '2024-03-31'
  AND NOT (p.admission_date BETWEEN '2024-03-01' AND '2024-03-31');
```

**Output:**

<img width="582" height="161" alt="image" src="https://github.com/user-attachments/assets/7ecf7b7d-51a9-48d0-8421-f8384a2c1d6d" />


**Question 9**
---
<img width="581" height="430" alt="image" src="https://github.com/user-attachments/assets/d307c6e3-c73e-4ef7-b954-36b3896ed10d" />


```sql
select c.cust_name as "Customer Name",
c.city,
s.name as "Salesman",
s.commission
from customer as c
inner join salesman as s
on c.salesman_id=s.salesman_id;
```

**Output:**

<img width="583" height="396" alt="image" src="https://github.com/user-attachments/assets/881d0bf9-edff-4746-a332-ef3ff343a91a" />


**Question 10**
---
<img width="580" height="426" alt="image" src="https://github.com/user-attachments/assets/1b54a592-efe5-4f84-8b8f-96d969ffeca5" />


```sql
select c.cust_name, c.city, c.grade,
s.name as "Salesman",s.city
from customer as c
inner join salesman as s
on c.salesman_id=s.salesman_id
group by c.customer_id;
```

**Output:**

<img width="583" height="384" alt="image" src="https://github.com/user-attachments/assets/7d1c2dc8-f1c6-40ea-83e0-86672c6d8efc" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
