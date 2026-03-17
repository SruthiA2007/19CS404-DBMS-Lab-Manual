# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="580" height="441" alt="image" src="https://github.com/user-attachments/assets/661707e7-fb9c-49b3-b71b-0744730001e7" />


```sql
select * from CUSTOMERS
where salary>1500;
```

**Output:**

<img width="583" height="282" alt="image" src="https://github.com/user-attachments/assets/7b3c7618-dd3d-47e3-ade9-e1bf06be70bc" />


**Question 2**
---
<img width="574" height="321" alt="image" src="https://github.com/user-attachments/assets/de1b309f-64b4-4fb3-bcec-bfe7ac556ced" />


```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(phone) = 1
);
```

**Output:**

<img width="506" height="396" alt="image" src="https://github.com/user-attachments/assets/530c9799-f1e9-42eb-8036-d9a03a752ff5" />


**Question 3**
---
<img width="585" height="355" alt="image" src="https://github.com/user-attachments/assets/1fe4015f-09b9-4f1a-8c5f-0876bef9d015" />


```sql
SELECT * FROM CUSTOMERS 
WHERE ID in(
select ID 
from CUSTOMERS
where ADDRESS = 'Delhi' AND AGE < 30);
```

**Output:**

<img width="579" height="174" alt="image" src="https://github.com/user-attachments/assets/af61ee76-ca85-473b-96fc-b128039d0a13" />


**Question 4**
---
<img width="581" height="407" alt="image" src="https://github.com/user-attachments/assets/85855ac4-6a57-4e5d-a95e-2eaf9abeb529" />

```sql
select * from CUSTOMERS
where salary<2500;
```

**Output:**

<img width="587" height="222" alt="image" src="https://github.com/user-attachments/assets/454dcc0c-97b2-4074-89d4-b0452a3a097b" />


**Question 5**
---
<img width="585" height="371" alt="image" src="https://github.com/user-attachments/assets/6a23906f-d0db-43a2-8faa-191e1a73e831" />


```sql
select ord_no,purch_amt,ord_date,customer_id,salesman_id
from orders
where salesman_id in(
select salesman_id
from salesman
where name='Paul Adam');
```

**Output:**

<img width="579" height="183" alt="image" src="https://github.com/user-attachments/assets/3983859f-15a8-43c9-9eef-df9dda17afb7" />

**Question 6**
---
<img width="581" height="239" alt="image" src="https://github.com/user-attachments/assets/c5748d6b-e943-4924-a8c4-75f3b6935d78" />


```sql
select grade, COUNT(*)
from customer
where grade>(
select avg(grade)
from customer
where city='New York')
group by grade;
```

**Output:**

<img width="494" height="277" alt="image" src="https://github.com/user-attachments/assets/84408ecc-0141-46f2-a23e-913268f9d3e1" />


**Question 7**
---
<img width="585" height="298" alt="image" src="https://github.com/user-attachments/assets/548e999d-6f15-4b7b-b5d2-77350c5e6b68" />


```sql
select name,city
from customer
where city in(
select city
from customer
where id in (3,7));
```

**Output:**

<img width="567" height="389" alt="image" src="https://github.com/user-attachments/assets/6344ff2f-2e6a-4c4f-a349-fd859d009505" />


**Question 8**
---
<img width="584" height="305" alt="image" src="https://github.com/user-attachments/assets/060349b6-5275-4466-ba32-76562c126ddd" />


```sql
select ord_no,purch_amt,ord_date, customer_id,salesman_id
from ORDERS
where purch_amt>(
select avg(purch_amt)
from ORDERS
where ord_date='2012-10-10');
```

**Output:**

<img width="581" height="215" alt="image" src="https://github.com/user-attachments/assets/036a5399-fd59-4342-9f81-a821e58731b7" />

**Question 9**
---
<img width="578" height="473" alt="image" src="https://github.com/user-attachments/assets/1e0c0f76-4c68-446f-b79d-f1c5fa776ec7" />


```sql
-- Paste your SQL code below for Question 9
```

**Output:**

<img width="586" height="274" alt="image" src="https://github.com/user-attachments/assets/379cbd12-1ffc-462a-bf9f-cb18aea88027" />


**Question 10**
---
<img width="581" height="384" alt="image" src="https://github.com/user-attachments/assets/a4209e79-b70f-4da7-960e-36c2204692b8" />


```sql
select ord_no,purch_amt,ord_date,salesman_id
from orders
where salesman_id in(
select salesman_id
from salesman
where commission=(select max(commission) from salesman));
```

**Output:**

<img width="584" height="251" alt="image" src="https://github.com/user-attachments/assets/918a7ea6-b1b1-40b8-aa2a-c794a221cd0b" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
