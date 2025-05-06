# SQL Learning Guide and Examples

## Basic SQL Concepts

### SELECT Statements
The `SELECT` statement is the most fundamental SQL command used to query data from a database. It specifies which columns you want to retrieve and from which table.

#### 1. Selecting All Columns

```sql
SELECT *
FROM Orders
````

This query retrieves all columns from the `Orders` table.

#### 2. Selecting Specified Columns

```sql
SELECT Product
FROM Orders
```

This query retrieves the `Product` column from the `Orders` table.

#### 3. Selecting Multiple Columns

```sql
SELECT Product, Quantity_Ordered, Price_Each
FROM Orders
```

This query retrieves the `Product`, `Quantity_Ordered`, and `Price_Each` columns.

#### 4. Using the `TOP` Clause

```sql
SELECT TOP 5 Product, Quantity_Ordered, Price_Each
FROM Orders
```

This query retrieves the first 5 rows from the `Orders` table.

#### 5. Using Aliases

```sql
SELECT Product AS Item, Quantity_Ordered AS Quantity, Price_Each AS Price
FROM Orders
```

This query renames the columns in the result set to `Item`, `Quantity`, and `Price`.

#### 6. Selecting Distinct Items

```sql
SELECT DISTINCT Purchase_Address
FROM Orders;
```

This query retrieves all unique `Purchase_Address` values.

```sql
SELECT DISTINCT Product, Order_Date
FROM Orders
```

This query retrieves all unique combinations of `Product` and `Order_Date`.

## Basic Filtering (The `WHERE` Clause)

To filter the rows based on certain conditions, use the `WHERE` clause.

### 1. Using a `WHERE` Clause with `=` (Equal to)

```sql
SELECT Order_ID, Product, Quantity_Ordered, Price_Each
FROM Orders
WHERE Product = 'USB-C Charging Cable'
```

This query selects orders where the product is `'USB-C Charging Cable'`.

### 2. Using a `WHERE` Clause with `<>` (Not Equal to)

```sql
SELECT *
FROM Orders
WHERE Product <> 'USB-C Charging Cable';
```

This query selects all orders where the product is not `'USB-C Charging Cable'`.

### 3. Using a `WHERE` Clause with `>` (Greater Than)

```sql
SELECT *
FROM Orders
WHERE Quantity_Ordered > 2
```

This query selects all orders where the quantity ordered is greater than 2.

### 4. Using a `WHERE` Clause with `<` (Less Than)

```sql
SELECT *
FROM Orders
WHERE Price_Each < 100
```

This query selects all orders where the price of each item is less than 100.

### 5. Using a `WHERE` Clause with `>=` (Greater Than or Equal to)

```sql
SELECT *
FROM Orders
WHERE Quantity_Ordered >= 5
```

This query selects all orders where the quantity ordered is greater than or equal to 5.

### 6. Using a `WHERE` Clause with `<=` (Less Than or Equal to)

```sql
SELECT *
FROM Orders
WHERE Price_Each <= 50
```

This query selects all orders where the price of each item is less than or equal to 50.

### 7. Using `BETWEEN`

```sql
SELECT *
FROM Orders
WHERE Order_Date BETWEEN '2019-08-28' AND '2019-11-09'
```

This query selects all orders where the order date is between `2019-08-28` and `2019-11-09`.

## The `IN` Syntax

The `IN` operator is used to filter data by checking if a value matches any value in a specified list.

```sql
SELECT *
FROM Orders
WHERE Product IN ('Wired Headphones', 'USB-C Charging Cable')
```

This query retrieves all orders where the product is either `'Wired Headphones'` or `'USB-C Charging Cable'`.

## Using the `AND` Syntax

The `AND` operator in SQL is used to combine multiple conditions from different columns in a `WHERE` clause. All conditions must be true for the rows to be included in the result set.

```sql
SELECT *
FROM Orders
WHERE Product = 'USB-C Charging Cable' AND Quantity_Ordered > 2;
```

This query selects all orders where the product is `'USB-C Charging Cable'` and the quantity ordered is greater than 2.

## Using the `LIKE` Syntax

The `LIKE` operator in SQL is used to search for a specified pattern in a column. It's particularly useful for filtering text data based on partial matches.

### 1. Using `%` (Wild Card for Any Characters)

```sql
SELECT *
FROM Orders
WHERE Product LIKE 'Wired%';
```

This query retrieves all orders where the `Product` starts with `'Wired'`.

### 2. Using `_` (Wildcard for a Specific Character)

```sql
SELECT *
FROM Orders
WHERE Product LIKE '_a%'
```

This query retrieves all orders where the `Product` has 'a' as the second character.

```sql
SELECT *
FROM Orders
WHERE Product LIKE '__h___'
```

This query retrieves all orders where the `Product` has exactly 5 characters, and the third character is 'h'.

```sql
SELECT *
FROM Orders
WHERE Product LIKE 'Go_________e'
```

This query retrieves all orders where the `Product` starts with 'G', has 'o' as the second character, and has exactly 12 characters.

---

This file serves as a guide to various SQL concepts, including basic SQL commands, filtering options, and pattern matching using `LIKE`. It's a great starting point for anyone learning SQL or refining their SQL query skills.

```

