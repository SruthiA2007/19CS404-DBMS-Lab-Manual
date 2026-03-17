# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="590" height="126" alt="image" src="https://github.com/user-attachments/assets/af098adc-5854-4b21-a067-a9815a7afd4b" />


```sql
INSERT INTO Products(ProductId,Name,Category,Price,Stock)
VALUES(101,'Laptop','Electronics',1500,50);
```

**Output:**

<img width="509" height="91" alt="image" src="https://github.com/user-attachments/assets/8ffa477a-9891-4afd-95f4-efbebaf4c2a6" />

<img width="302" height="97" alt="image" src="https://github.com/user-attachments/assets/b8602a59-fb65-4652-8da4-57d2365d0d56" />

**Question 2**
---
<img width="506" height="173" alt="image" src="https://github.com/user-attachments/assets/6391d0b3-8110-4cec-904b-be800b4126d4" />


```sql
CREATE TABLE Invoices(
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    DueDate DATE,
    Amount REAL,
    CHECK(DueDate>InvoiceDate),
    CHECK(Amount>0)
);
```

**Output:**

<img width="591" height="320" alt="image" src="https://github.com/user-attachments/assets/8c2461a4-4135-467c-a4e3-ff20e7dbc94f" />


**Question 3**
---
<img width="585" height="226" alt="image" src="https://github.com/user-attachments/assets/da28fed2-3237-4555-91ec-400d8ef198d0" />


```sql
ALTER TABLE Companies
RENAME COLUMN name TO first_name;
ALTER TABLE Companies
ADD mobilenumber number;
ALTER TABLE Companies
ADD DOB Date;
ALTER TABLE Companies
ADD State varchar(30);
```

**Output:**

<img width="588" height="483" alt="image" src="https://github.com/user-attachments/assets/8d7c86bd-3c9b-438a-8dbc-badaaff27d0b" />


**Question 4**
---
<img width="574" height="295" alt="image" src="https://github.com/user-attachments/assets/bb5efbfc-953e-4dbb-a7ad-a0abe955f51f" />


```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(202,'Ella King','F','Chemistry',87);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(203,'James Bond','M','Literature',78);
```

**Output:**

<img width="583" height="324" alt="image" src="https://github.com/user-attachments/assets/a9655af3-19aa-4608-9230-d9653d547363" />

**Question 5**
---
<img width="583" height="280" alt="image" src="https://github.com/user-attachments/assets/798a2c25-2a01-45f4-989c-67c20f6f8e55" />


```sql
CREATE TABLE Products(
    ProductID INTEGER,
    ProductName TEXT,
    Price REAL,
    Stock INTEGER
);
```

**Output:**

<img width="579" height="363" alt="image" src="https://github.com/user-attachments/assets/d6b6e3ec-04b0-42bc-89c2-5b85b26ec31a" />


**Question 6**
---
<img width="582" height="204" alt="image" src="https://github.com/user-attachments/assets/37fabb06-1454-4fec-a500-63f3d72e4b53" />


```sql
ALTER TABLE Student_details
ADD Date_of_birth Date;
```

**Output:**

<img width="576" height="427" alt="image" src="https://github.com/user-attachments/assets/01c32abd-cf86-4110-b722-b666d6dfdc6f" />


**Question 7**
---
<img width="579" height="213" alt="image" src="https://github.com/user-attachments/assets/54ec016f-b0db-4815-9e35-d93571fa0d0d" />


```sql
INSERT INTO Books(ISBN, Title, Author, Publisher,YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;
```

**Output:**

<img width="581" height="317" alt="image" src="https://github.com/user-attachments/assets/6c0b027a-4102-4509-88d5-bb5a5e0057d1" />


**Question 8**
---
<img width="581" height="152" alt="image" src="https://github.com/user-attachments/assets/7c91defa-c511-4158-b232-83363e5da584" />


```sql
CREATE TABLE Department(
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT UNIQUE NOT NULL,
    Location TEXT
    );
```

**Output:**

<img width="588" height="267" alt="image" src="https://github.com/user-attachments/assets/be2adfa9-4c9f-4b82-a22a-6896a27808b3" />


**Question 9**
---
<img width="581" height="138" alt="image" src="https://github.com/user-attachments/assets/81ff9f76-7234-4ec0-b1fe-2311123e2716" />


```sql
CREATE TABLE Orders(
    OrderID INTEGER PRIMARY KEY,
    OrderDate DATE NOT NULL,
    CustomerID INTEGER,
    FOREIGN KEY (CustomerID) REFERENCES
 Customers(CustomerID)
);
```

**Output:**

<img width="588" height="328" alt="image" src="https://github.com/user-attachments/assets/bad98c72-f344-4f81-b08e-a0aa92584a3c" />


**Question 10**
---
<img width="575" height="270" alt="image" src="https://github.com/user-attachments/assets/51589f8f-919b-4a4a-81fb-09c3d1774904" />


```sql
CREATE TABLE item(
    item_id TEXT PRIMARY KEY,
    item_desc TEXT,
    rate INTEGER,
    icom_id TEXT(4),
    FOREIGN KEY(icom_id) REFERENCES
company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
);
```

**Output:**

<img width="581" height="151" alt="image" src="https://github.com/user-attachments/assets/1ed0d1fe-24de-4e41-babd-14914e8696af" />

***RESULT***
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
