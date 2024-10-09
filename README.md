# SQL
string fictions documentaions - https://www.postgresql.org/docs/9.1/functions-string.html

In SQL, the `%` symbol is a wildcard character used with the `LIKE` operator to represent zero, one, or multiple characters in a string. It is used for pattern matching in string comparisons.

Here's what `%` does in SQL:

- `%` matches any sequence of characters, including zero characters.
- If you place `%` at the beginning of the pattern, it matches any sequence of characters at the end of the string.
- If you place `%` at the end of the pattern, it matches any sequence of characters at the beginning of the string.
- If you place `%` at both the beginning and the end of the pattern, it matches any sequence of characters in the middle of the string.

For example:

- `%word` matches any string that ends with "word".
- `word%` matches any string that begins with "word".
- `%word%` matches any string that contains "word" anywhere within it.

This makes `%` a powerful tool for searching and filtering strings based on patterns rather than exact matches.

 Write your MySQL query statement below
Select patient_id , patient_name , conditions 
from Patients 
where conditions like '%DIAB1%'
OR 
 conditions like 'DIAB1%'
OR 
conditions like '%DIAB1'



Example 1: Cumulative Sum using PRECEDING
```
Let's say you have a sales table, and you want to calculate the cumulative sum of sales for the current row and the previous two rows.

sql
Copy code
SELECT 
    order_id,
    amount,
    SUM(amount) OVER (
        ORDER BY order_id
        ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
    ) AS cumulative_sales
FROM sales;
```

Example 3: Custom Range Using Both PRECEDING and FOLLOWING
You can define a custom range that includes both rows before and after the current row. For example, calculating a moving total that includes the current row, the two preceding rows, and the next row.
```
sql
Copy code
SELECT 
    order_id,
    amount,
    SUM(amount) OVER (
        ORDER BY order_id
        ROWS BETWEEN 2 PRECEDING AND 1 FOLLOWING
    ) AS moving_total
FROM sales;
Explanation:
ROWS BETWEEN 2 PRECEDING AND 1 FOLLOWING: The sum includes two rows before, the current row, and one row after.

```
![image](https://github.com/Ayush-Tibrewal/SQL/assets/96817905/74d2fecf-35f3-4595-9f53-64f1a0692ed5)


<>	Not equal to operaotor 


PRECEDING AND BETWEEN TERM -https://www.youtube.com/watch?v=xLAmRI_Iky8


 # REGREX
https://www.geeksforgeeks.org/mysql-regular-expressions-regexp/


#DATE_FORMAT
https://www.geeksforgeeks.org/date_format-function-in-mysql/
// used in eum
# if condition in sql 
```
Return 5 if the condition is TRUE, or 10 if the condition is FALSE:
IF(condition, value_if_true, value_if_false)
SELECT IF(500<1000, 5, 10);
```
```
Subtract 10 days from a date and return the date:

SELECT DATE_SUB("2017-06-15", INTERVAL 10 DAY);
// where caluse k satth use karlo toh ye jo bhi date ek se kaam hai ya kisi se bhi kaam leni ho uske liye use kr sakte hai 
```

```
Return the remainder of 18/4:

SELECT MOD(18, 4);
```
```
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;


```
![image](https://github.com/user-attachments/assets/12c5902e-6242-45a1-9e34-426d4caac8bc)


 UNION only returns a unique record, while UNION ALL returns all the records (including duplicates) , MIN() function returns the minimum number  ,MOD(ID , 1) IS ALSO THE FUNCTION  WORK AS MODULUS 
 ## using keyboard 
 it is using instead of ON
```
 SELECT *
FROM users
JOIN orders USING (user_id)
WHERE user_id = 1;
```
## between operator 
```
Selects all products with a price between 10 and 20:
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;
```
## is null vs COALESCE()
Function: ISNULL is used to replace NULL with a specified replacement value.
Syntax: ISNULL(expression, replacement_value)

Function: COALESCE returns the first non-null expression among its arguments.
Syntax: COALESCE(expression1, expression2, ..., expressionN)

```
ISNULL(department_id, 0)
// jo bhi null hoga department mein uski jagha 0 ajayega


 COALESCE(column1, column2, column3, 'default_value')
FROM table_name;
//This query returns the first non-null value among column1, column2, and column3. If all are null, it returns 'default_value'
```
## extract fuction in sql 
```
SELECT EXTRACT(YEAR FROM '2020-07-15 08:06:44') AS Yr;  
toh year dedega 
```
length of the words 
where LENGTH(content)>15;
## group concatnate 
```
GROUP_CONCAT(expression [ORDER BY expression] [SEPARATOR separator])
Leadership, Punctuality, Quick-learner, Responsible jab aise kaane ho
GROUP_CONCAT ( DISTINCT strength)
```
![image](https://github.com/user-attachments/assets/7abf3bb4-2d60-4f91-8e0f-1bbe11b59151)

## substring , left , rigth 
```
SUBSTRING(field_name, starting position, ending position relative to the starting position)
left (name of the coloum , kitne left side k rakhne hai )
same with
right()
```
## natural join 
A natural join is a type of join operation that creates an implicit join by combining tables based on columns with the same name and data type. It is similar to the INNER or LEFT JOIN, but we cannot use the ON or USING clause with natural join as we used in them.


