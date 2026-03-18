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
<img width="1280" height="965" alt="image" src="https://github.com/user-attachments/assets/646186c8-662e-4bdb-9d8c-811a56ac05d9" />


```sql
SELECT 
    c.cust_name AS "cust_name",
    c.city AS "city",
    o.ord_no AS "ord_no",
    o.ord_date AS "ord_date",
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;
```

**Output:**

<img width="1258" height="973" alt="image" src="https://github.com/user-attachments/assets/a902626e-1640-456c-9f8c-9229ceb951fc" />


**Question 2**
---
<img width="1268" height="510" alt="image" src="https://github.com/user-attachments/assets/cd892540-520a-415d-8aa4-dda687b558df" />


```sql
SELECT 
    p.first_name AS patient_name,
    t.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id
WHERE p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="1276" height="400" alt="image" src="https://github.com/user-attachments/assets/e2658ca9-be08-4906-8e81-4f82e96772fd" />


**Question 3**
---
<img width="1276" height="630" alt="image" src="https://github.com/user-attachments/assets/863cf914-02e6-464a-b3a9-0d89abbdb2bb" />


```sql
SELECT 
    p.first_name AS patient_name,
    d.specialization AS Doctor_specialization
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="627" height="397" alt="image" src="https://github.com/user-attachments/assets/f2244bdf-a8b6-4205-8819-d1ef8847462f" />


**Question 4**
---
<img width="1258" height="509" alt="image" src="https://github.com/user-attachments/assets/5501c8bf-1c10-4dbd-a5fd-2c2aa23e99ce" />


```sql
SELECT p.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id
WHERE t.test_date BETWEEN '2024-03-01' AND '2024-03-31';
```

**Output:**

<img width="1292" height="409" alt="image" src="https://github.com/user-attachments/assets/35430a4f-135a-4e0b-9027-bc5b12a48a09" />


**Question 5**
---
<img width="1283" height="491" alt="image" src="https://github.com/user-attachments/assets/1a50d7ec-8cce-4a22-972f-8e387f07648c" />


```sql
SELECT p.*
FROM patients p
INNER JOIN appointments a
ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="1286" height="409" alt="image" src="https://github.com/user-attachments/assets/381b6cae-e89c-4370-8967-ff62b73ece4d" />


**Question 6**
---
<img width="1269" height="484" alt="image" src="https://github.com/user-attachments/assets/aaa87b25-19ba-49f6-9bf8-2e67c40db2c5" />


```sql
SELECT p.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id
WHERE t.test_name = 'X-Ray'
AND t.result = 'Normal';
```

**Output:**

<img width="1265" height="408" alt="image" src="https://github.com/user-attachments/assets/a1863b8e-66a8-447c-9b82-51c0b04d32e1" />


**Question 7**
---
<img width="1274" height="501" alt="image" src="https://github.com/user-attachments/assets/34e8d404-963e-4bc2-a29d-75b5a8e8ecf4" />


```sql
SELECT p.*
FROM patients p
INNER JOIN appointments a
ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-02-01' AND '2024-02-28';
```

**Output:**

<img width="1277" height="405" alt="image" src="https://github.com/user-attachments/assets/720451af-5bba-4360-bf90-aa622c6233c8" />

**Question 8**
---
<img width="1254" height="504" alt="image" src="https://github.com/user-attachments/assets/6d41cb44-bca4-40bf-802b-1af2569b2bfa" />

```sql
SELECT 
    n.nurse_id,
    d.department_name
FROM nurses n
INNER JOIN departments d
ON n.department_id = d.department_id
WHERE n.first_name = 'David'
AND n.last_name = 'Moore';
```

**Output:**

<img width="622" height="388" alt="image" src="https://github.com/user-attachments/assets/e6def213-28d7-44e3-9595-74a9c5fd59ca" />

**Question 9**
---
<img width="1275" height="538" alt="image" src="https://github.com/user-attachments/assets/852f021a-a4fd-4919-b5b8-a27e5b4982a0" />

```sql
SELECT 
    p.first_name AS patient_name,
    t.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id;
```

**Output:**

<img width="1276" height="522" alt="image" src="https://github.com/user-attachments/assets/bd8d79e4-f698-4799-b258-8b1865ae677f" />

**Question 10**
---
<img width="1267" height="607" alt="image" src="https://github.com/user-attachments/assets/42a6c051-5773-4f04-a44c-2cdf4d4acb8a" />

```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NOT NULL;
```

**Output:**

<img width="628" height="371" alt="image" src="https://github.com/user-attachments/assets/ce8bdc5d-e1d6-44a6-893e-ad25f525743e" />

**SEB 5 SS **

<img width="1399" height="66" alt="image" src="https://github.com/user-attachments/assets/9bd88c28-ff1b-4fe4-9c41-baf5342844a5" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
