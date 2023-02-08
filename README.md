
<!-- Logo-->
<p align="center">
<img src="https://1000logos.net/wp-content/uploads/2020/08/MySQL-Logo.png" width="250" height="156" align="center" />
</p>

   
# My "MySQL" Notes

I started learning MySQL as a part of advanced web developer learning. Heres all my notes and cheats for MySQL.


<!-- Syntaxes -->

# Syntaxes

- <a href='#select'>SELECT</a>
   - <a href='#as'>AS</a>
   - <a href='#distinct'>DISTINCT</a>
- From
- WHERE
 
 
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
#### Output:
   
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
#### Output:
   
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
#### Output:

![](./Assets/03distinctexmpl.png) 

```javascript
SELECT DISTINCT state
FROM sql_store.customers;
```
#### Output:

![](./Assets/04distinctexmpl.png) 
   
</div>
