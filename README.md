<div id='top'>
   
</br></br>  

<!-- Logo-->
<p align="center">
<img src="https://1000logos.net/wp-content/uploads/2020/08/MySQL-Logo.png" width="250" height="156" align="center" />
</p> 
   
</br> </br></br>

   
# My "MySQL" Notes  Day-5

I started learning MySQL as a part of advanced web developer learning. Heres all my notes and cheats for MySQL. </br>
<a href='https://github.com/Xoaib007/MySQL-Notes/tree/main/Assets/Materials'>Materials I used to demonstrate the examples.
   
</br>

# Table of Contents

- [Syntax](https://github.com/Xoaib007/MySQL-Notes/blob/main/Syntax.md)
- [Concepts](#concepts)

</br>


# What is MySQL ?
   
MySQL is an open source SQL relational database management system that’s developed and supported by Oracle. Usually MySQL uses tables to store datas connects it with “keys”.  
   
```sql
SELECT *
FROM sql_inventory.products;
```
Basic MySQL statement. </br>

</br>

# Concepts

- [Join concept](#join-concept)
    
    </br>
    
## Join Concept

The join we learnt in clause section is called Inner Join. There is also other types of Join in SQL.

- [Types](#Types-of-the-joins-in-sql)
- [Use cases]
- [Alternative Methods](#alternative-methods-of-join)

## Types of the JOINs in SQL

- [INNER JOIN](#inner-join)
- [OUTER JOIN](#outer-join)
   - [LEFT JOIN](#left-join)
   - [RIGHT JOIN: Returns all records from the right table, and the matched records from the left table]
   - [FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table]
    
    </br>
    
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
    
    </br>
    
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
    
    </br>
    
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

</br>

## Alternative Methods of JOIN

- [Implicit Join](#implicit-join)
- [NATURAL JOIN](#natural-join)


### NATURAL JOIN

Another way of joining table is NATURAL JOIN. In this method we dont have to mention the matching columns in ON clause. SQL will automaticly find the matching column by their name and join them. </br>
This might seems very easy and efficient but this method is not recomended at all. This is a bit dengerous. Because we are giving away the whole control to MySQL engene, which may produce some unexpected results.

```sql
SELECT 
order_id,
first_name, 
last_name
FROM sql_store.orders
NATURAL JOIN sql_store.customers
```
Output:

![image](https://user-images.githubusercontent.com/55616502/218291737-f7df2c58-5da2-445e-9836-f75855e0573b.png)

</br>

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

</br>

<p align='center'>
   </br>  </br>  </br>  </br>
   <a href='#top'>Go to top
</p>
