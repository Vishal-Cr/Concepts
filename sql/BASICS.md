# Basics of SQL :rocket:
### Select Queries
```
- Select *  From <DatabaseName>
selects All
- Select <Column-Name> From <DatabaseName>
- Select <col1>, <col2> From <DatabaseName>
```
#### 1. Queries With Constraints (usefulf for numerical column values):
- used for filtering results.
```- Operator (=,!=,<=,>=,<,>) standard numerical operators
- BETWEEN...AND...
- NOT BETWEEN...AND...
- IN(...)
- NOT IN(...)
```
- For more complex condition AND, OR can be used.
#### 2. For text columns SQL uses:
- SQL uses case-insensitive and wild card mathing for text related to column matching.
```
= Case sensitive string comparison
!= or <> - Case Sensitive
% - Used anywhere in a string to match a sequence of zero or more characters(only with LIKE or NOT LIKE)
LIKE/ NOT LIKE  - Case insensitive exact string comparison, 

```

- `DISTINCT` keyword is used to discard duplicate rows blingly.
- In addition `Group By` is used to discard duplicates based on certain columns.
#### Ordering Result
- In most databases the data is added in no particular column order.
- `ORDER BY`  command is used, in PostGreSql Null can be placed in first or last as,        NULLS LAST or NULLS FIRST;
- ORDER BY is used in addition with `LIMIT` and `OFFSET` .
```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```
- LIMIT reduces the number of rows to return.
- OFFSET will specify where to begin counting from.
```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
:warning:  Negative values can be used in the `Offset` ex: -4 will show last 4 rows, However it's not supported by every language.

### LEARNT SO FAR :hourglass:
- So far, the basic queries involve these queries
`SELECT,FROM,WHERE,ORDER BY,LIMIT`
- :exclamation: SYNTAX of limit: ` LIMIT [offset,]row_count`

## Working With Multiple Tables
- Data Normalization
- Tables that share a single entity should have a primary key that uniquely identifies the entity.
- Using JOIN
```
SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
#### INNER JOINS :link:
- INNER JOIN is the process that matches rows from the first row and second row with the same entity id(Defined by the `ON` constraint) and creates a row which includes all the columns from the rows.
#### OUTER JOINS :link:
LEFT,RIGHT,FULL
### Queries with Expression

WHERE (...) AS ...

### Queries With Aggregate 
Max,SUM,AVG,COUNT are called aggregate Function.

### Creating A Table :hammer:
Create table statement w/ optional table constraint and default value
```CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
////////////EXAMPLE//////////////////
CREATE TABLE movies (
    id INTEGER PRIMARY KEY,
    title TEXT,
    director TEXT,
    year INTEGER, 
    length_minutes INTEGER
);

```
# POSTGRESQL :elephant:
- Dont't use Double quotes in postgresql queries, use single quotes.
- The IN query in SQL is useful in ommitting OR from qeury.
```
for EX:
Select * from facilites
WHERE facid IN (1,5);

this will give all data with facid with 1, 5;
``



