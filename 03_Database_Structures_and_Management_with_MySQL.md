# Module 1 - Intro to MySQL
## 1. Filtering data
`WHERE` Clause 
> __Used withing an SQL `SELECT` statement to determine how data is filtered in a table__

### Logical operator 
=> `AND` // `OR` // `NOT` // `IN` // 

`BETWEEN`

Example - with Date
> When filtering dates, be sure to use `CAST` function to explicitly convert the values to dates
```
  SELECT *
  FROM order_details
  WHERE order_date BETWEEN CAST('2014-02-01' AS DATE) AND CAST('2014-02-28' AS DATE);
```
**Note**: the order_date field is of type DATE and not of type DATETIME => This is why we do not have to CAST the oder_date field to a DATE type

Example - Combine NOT and BETWEEN
```
  SELECT *
  FROM suppliers
  WHERE supplier_id NOT BETWEEN 2000 AND 2999;
```
**Note**: it is equivalent to `WHERE supplier_id < 2000 OR supplier_id > 2999;`

`LIKE`
* The % wildcard matches zero or more characters.
* The _ wildcard matches a single character.
* Use ESCAPE clause specifies an escape character other than the default escape character (\).
* Use the NOT operator to negate the LIKE operator.

Example - Use LIKE with `ESCAPE`
> * ESCAPE clause is to specify the escape character so that the LIKE operator interprets the wildcard character as a literal character.
> * the backslash character (\) is the default escape character, if ESCAPE is not used explicitly.
```
  SELECT productCode, productName
  FROM products
  WHERE productCode LIKE '%\_20%';
```

```
  SELECT productCode, productName
  FROM products
  WHERE productCode LIKE '%$_20%' ESCAPE '$';
```

## 2. Joining Tables


## 3. Grouping Data



-----
# Module 2 - Updating databases and working with views


-----
# Module 3 - Function and MySQL stored procedure

-----
# Moule 4 - Graded Assessment
