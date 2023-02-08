
<!-- Logo-->
<p align="center">
<img src="https://1000logos.net/wp-content/uploads/2020/08/MySQL-Logo.png" width="250" height="156" align="center" />
</p>

   
# My "MySQL" Notes

I started learning MySQL as a part of advanced web developer learning. Heres all my notes and cheats for MySQL.

# Table of Contents

- <a href='#syntax'>Syntax</a>


<!-- Syntaxes -->

<div id='syntax'>
   
# Syntax

- <a href='#select'>SELECT</a>
   - <a href='#as'>AS</a>
   - <a href='#distinct'>DISTINCT</a>
- From
- <a href='#where'>WHERE</a>

</div>
 
<!-- Select -->
<div id='select'>

## SELECT

SELECT statements select data from one or more tables.

```javascript
<!-- use asterix (*) to get all the data from the table -->
SELECT *
FROM sql_inventory.products;
```

```javascript
SELECT 
name,
unit_price
FROM sql_inventory.products;
```
Output:
   
![](./Assets/01selectexmpl.png)
</div>

   
<!-- AS -->
<div id='as'>
   
### AS
   
AS command can rename a column and name a new collumn.
   
```javascript
 SELECT 
 name,
 unit_price,
 unit_price * 1.1 AS new_price
 FROM sql_inventory.products;
```
Output:
   
![](./Assets/02asexmpl.png) 
   
</div>

<!-- Distinct -->

<div id='distinct'>

### AS

DISTINCT clause remove the duplocate data.

```javascript
SELECT state
FROM sql_store.customers;
```
Output:

![](./Assets/03distinctexmpl.png) 

```javascript
SELECT DISTINCT state
FROM sql_store.customers;
```
Output:

![](./Assets/04distinctexmpl.png) 
   
</div>

<!-- where -->

<div id='where'>

   ## WHERE

The WHERE clause is used to filter records.

```javascript
SELECT *
FROM sql_store.orders
WHERE customer_id = 10
```
Output:

![](./Assets/05whereexmpl.png) 

### MuSQL Logical Operators:
   - <a href='#and'>AND
   - <a href='#and'>OR
   - <a href='#not'>NOT
   - <a href='#in'>IN
   - <a href='#and'>NOT IN
   - <a href='#between'>BETWEEN
   - <a href='#like'>LIKE
   - <a href='#regexp'>REGEXP

<div id='and'>
   
#### AND operator

```javascript
SELECT *
FROM sql_store.orders
WHERE customer_id = 10 AND status > 1
```
Output:

![](./Assets/06whereexmpl.png) 

</div>
   
<div id='not'>
   
#### NOT operator
   
```javascript
<!-- NOT operator doest the oposite of the condition -->
SELECT *
FROM sql_store.orders
WHERE NOT customer_id = 10 AND status > 1
```
Output:

![](./Assets/07whereexmpl.png)
   
</div>
   
<div id='in'>
  
#### IN operator
   
```javascript
SELECT *
FROM sql_store.orders
<!-- WHERE customer_id = 10 OR  customer_id = 5 OR customer_id = 6-->
WHERE customer_id IN (10 , 5 , 6)
```
Output:

![](./Assets/08whereexmpl.png)
   
</div>
   
<div id='between'>
   
#### BETWEEN operator
   
```javascript
SELECT DISTINCT *
FROM sql_store.customers
WHERE birth_date between '1990-01-01' AND '2000-01-01'
```
Output:

![](./Assets/07whereexmpl.png) 
   
</div>
   
<div id='like'>
   
#### LIKE operator
   
```javascript
SELECT DISTINCT *
FROM sql_store.customers
<!--   % means there can be any number of charecter after 'B'  -->
WHERE first_name LIKE 'B%'
```
Output:

![](./Assets/07whereexmpl.png) 
   
```javascript
SELECT DISTINCT *
FROM sql_store.customers
<!--   5 _ means there will be exactly 5 charecter after 'B'  -->
WHERE first_name LIKE 'B_____'
```
Output:

![](./Assets/07whereexmpl.png) 
   
</div>
   
</div>
