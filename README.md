<div id='top'>
   
</br></br>  

<!-- Logo-->
<p align="center">
<img src="https://1000logos.net/wp-content/uploads/2020/08/MySQL-Logo.png" width="250" height="156" align="center" />
</p> 
   
</br> </br></br>

   
# My "MySQL" Notes  Day-4

I started learning MySQL as a part of advanced web developer learning. Heres all my notes and cheats for MySQL. </br>
<a href='https://github.com/Xoaib007/MySQL-Notes/tree/main/Assets/Materials'>Materials I used to demonstrate the examples.
   
</br>

# Table of Contents

- [Introduction](#what-is-mysql)
- [Syntax](#syntax)
- [Concepts](#concepts)

</br>


# What is MySQL
   
MySQL is an open source SQL relational database management system that’s developed and supported by Oracle. Usually MySQL uses tables to store datas connects it with “keys”.  
   
```sql
SELECT *
FROM sql_inventory.products;
```
Basic MySQL statement. </br>

</br>

# Syntax

- [SELECT](#select)
   - [AS](#as)
   - [DISTINCT](#distinct)
- From
- [WHERE](#where)
   - [Logical Operators](#mysql-logical-operators-and-functions)
- [ORDER BY](#order-by)
   - [DESC](#desc)
- [LIMIT](#limit)

</br>

## SELECT

SELECT statements select data from one or more tables.

```sql
-- use asterix (*) to get all the column from the table
SELECT *
FROM sql_inventory.products;
```

```sql
SELECT 
name,
unit_price
FROM sql_inventory.products;
```
Output:
   
![image](https://user-images.githubusercontent.com/55616502/217871673-a98a548e-1598-47d1-ba14-5cf8578cb7a0.png)

</br>

### AS
   
AS command can rename a column and name a new collumn.
   
```sql
 SELECT 
 name,
 unit_price,
 unit_price * 1.1 AS new_price
 FROM sql_inventory.products;
```
Output:
   
![image](https://user-images.githubusercontent.com/55616502/217871801-8bba5915-234d-4533-9927-41ff362d2470.png) 


### DISTINCT

DISTINCT clause remove the duplocate data.

```sql
-- without DISTINCT
SELECT state
FROM sql_store.customers;
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217872017-a5becefc-2795-47b0-bf6b-665f96f3cf04.png)

```sql
-- with DISTINCT
SELECT DISTINCT state
FROM sql_store.customers;
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217872128-b4598c73-22fc-4213-9411-bb0f95929ece.png)


## WHERE

The WHERE clause is used to filter records.

```sql
SELECT *
FROM sql_store.orders
WHERE customer_id = 10
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217872550-7b682676-2ba5-4db6-b106-002131ec7511.png) 

## MySQL Logical Operators and Functions
- [AND](#and)
- <a href='#or'>OR
- <a href='#not'>NOT
- <a href='#in'>IN
- <a href='#notin'>NOT IN
- <a href='#between'>BETWEEN
- <a href='#like'>LIKE
- <a href='#regexp'>REGEXP
- <a href='#isnull'>IS NULL
- <a href='#isnotnull'>IS NOT NULL
   
### AND operator
   
AND operator compares two expressions and returns true if both of the expressions are true.

```sql
SELECT *
FROM sql_store.orders
WHERE customer_id = 10 AND status > 1
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217868680-484c4b46-d255-40e7-a4ff-86dfece4ba73.png)

### OR operator
   
OR operator compares two expressions and returns TRUE if either of the expressions is TRUE.

```sql
SELECT *
FROM sql_store.orders
WHERE customer_id = 10 OR status > 1
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217868841-6407d8ca-55cf-42d4-be4d-55492d843634.png)
   
### NOT operator
   
NOT operator reverses or negates the input.
   
```sql
-- NOT operator doest the oposite of the condition
SELECT *
FROM sql_store.orders
WHERE NOT customer_id = 10 AND status > 1
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217869018-edd7f810-33b8-4e7c-8e3b-114ee3f9935a.png)
  
### IN function
   
IN() function finds a match in the given arguments.
   
```sql
SELECT *
FROM sql_store.orders
-- WHERE customer_id = 10 OR  customer_id = 5 OR customer_id = 6
WHERE customer_id IN (10 , 5 , 6)
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217868201-0427dddb-68b0-4ca8-bb89-d506fea0a8ce.png)

### NOT IN function

NOT IN() makes sure that the expression proceeded does not have any of the values present in the arguments.
   
```sql
SELECT *
FROM sql_store.orders
WHERE customer_id NOT IN (10 , 5 , 6)
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217867462-027dd6bb-589f-4668-abfc-9c5e12c544be.png)
   
### BETWEEN operator
   
BETWEEN... AND operator checks whether a value is within a range.
   
```sql
SELECT DISTINCT *
FROM sql_store.customers
WHERE birth_date BETWEEN '1990-01-01' AND '2000-01-01'
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217867213-f9ae258e-f3c1-4d7f-8f33-435f0c54dfae.png)
   
### LIKE operator
   
LIKE operator is used in a WHERE clause to search for a specified pattern in a column.
   
```sql
SELECT DISTINCT *
FROM sql_store.customers
--  % means there can be any number of charecter after 'B'
WHERE first_name LIKE 'B%'
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217866676-bfd1899d-75a0-4b26-9076-27f83ea70112.png)
   
```sql
SELECT DISTINCT *
FROM sql_store.customers
--  5 _ means there will be exactly 5 charecter after 'B'
WHERE first_name LIKE 'B_____'
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217866496-06179544-c71e-4593-9509-2116bf621433.png)
   
### REGEXP operator
   
REGEXP performs a pattern match of a string expression against a pattern. The pattern is supplied as an argument.
   
 <a href='https://github.com/Xoaib007/MySQL-Notes/blob/main/REGEXP.md'>know REGEXP in details

   
### IS NULL operator
   
IS NULL Condition is used to test for a NULL value.
   
```sql
SELECT * 
FROM sql_store.orders
WHERE shipped_date IS NULL
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217864970-1bf0fd48-ebc6-4ddc-a9b2-0e83ad5d1b63.png)
   
### IS NOT NULL operator
   
IS NOT NULL condition is used to test for a value that is not null.
   
```sql
SELECT * 
FROM sql_store.orders
WHERE shipped_date IS NOT NULL
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217864768-5bfb0cb9-72a8-423d-a1f7-36ab933728e8.png)
   
## ORDER BY
   
ORDER BY clause is used to sort the records in your result set. By default ORDER BY sets data in ascending order.
   
```sql
SELECT *
FROM sql_store.products
ORDER BY unit_price
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217863645-9ce6f440-303c-4120-85ad-81ec6b991f16.png)
   
### DESC
   
DESC keyword sorts the records in descending order.
   
```sql
SELECT *
FROM sql_store.products
ORDER BY unit_price DESC
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217863771-4e2a44e0-58e4-4a64-84bd-a92fd5c682f2.png)
   
## LIMIT
   
LIMIT clause is used to specify the number of records to return.
   
```sql
SELECT DISTINCT *
FROM sql_store.customers
ORDER BY points DESC
LIMIT 0, 3
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217863416-d79ef5c2-7f4f-4706-9d0b-ff6d22da4181.png)

# Concepts

- [Join concept](#join-concept)
    
## Join Concept

The join we learnt in clause section is called Inner Join. There is also other types of Join in SQL.

### Types of the JOINs in SQL:

- [INNER JOIN](#inner-join)
- [OUTER JOIN](#outer-join)
   - [LEFT JOIN](#left-join)
   - [RIGHT JOIN: Returns all records from the right table, and the matched records from the left table]
   - [FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table]
    
### INNER JOIN
   
JOIN clause is used to combine rows from two or more tables, based on a related column between them. It returns records that have matching values in both tables
   
```sql
SELECT 
order_id,
first_name, 
last_name
FROM sql_store.orders
JOIN sql_store.customers
ON orders.customer_id = customers.customer_id
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217862510-20c8c8a1-d99b-49bc-830c-950edc519094.png)
   
##### You can also join multiple number of tables.

```sql
SELECT 
order_id,
first_name, 
last_name
FROM sql_store.orders
JOIN sql_store.customers
ON orders.customer_id = customers.customer_id
```
   
![image](https://user-images.githubusercontent.com/55616502/217963459-5290e02a-40de-4a2c-94a2-d4e53d67f6b5.png)
    
       
### Implicit Join
   
Theres another method to join tables. This is quite simple but not recommended. In this method we use WHERE clause instead of JOIN.
   
```sql
SELECT 
order_id,
first_name, 
last_name
FROM sql_store.orders o, sql_store.customers c
Where o.customer_id = c.customer_id
```
    
### OUTER JOIN
#### LEFT JOIN

LEFT JOIN Returns all records from the left table, and the matched records from the right table.
This type of join returns all rows from the LEFT-hand table specified in the ON condition and only those rows from the other table where the joined fields are equal (join condition is met).
   
```sql
SELECT 
order_id,
first_name, 
last_name
FROM sql_store.orders
JOIN sql_store.customers
ON orders.customer_id = customers.customer_id
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217862510-20c8c8a1-d99b-49bc-830c-950edc519094.png)
    
#### RIGHT JOIN

RIGHT JOIN Returns all records from the right table, and the matched records from the right table. </br>
In two words, RIGHT JOIN does exactly opposit of what LEFT JOIN does.
   
```sql
SELECT 
order_id,
first_name, 
last_name
FROM sql_store.orders
JOIN sql_store.customers
ON orders.customer_id = customers.customer_id
```
Output:

![image](https://user-images.githubusercontent.com/55616502/217862510-20c8c8a1-d99b-49bc-830c-950edc519094.png)
   
<p align='center'>
   </br>  </br>  </br>  </br>
   <a href='#top'>Go to top
</p>
