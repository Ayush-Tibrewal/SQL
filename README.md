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
