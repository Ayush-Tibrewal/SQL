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

# Write your MySQL query statement below
Select patient_id , patient_name , conditions 
from Patients 
where conditions like '%DIAB1%'
OR 
 conditions like 'DIAB1%'
OR 
conditions like '%DIAB1'


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




 UNION only returns a unique record, while UNION ALL returns all the records (including duplicates) , MIN() function returns the minimum number 
