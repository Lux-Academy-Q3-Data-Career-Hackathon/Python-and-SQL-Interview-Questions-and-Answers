SQL INTERVIEW QUESTIONS

---

#### 1. What is the difference between INNER JOIN and OUTER JOIN in SQL?
+ **INNER JOIN** returns only the rows that have matching values in both tables.
+ **OUTER JOIN** returns all the rows from one table
and the matching rows from the other table (can be LEFT, RIGHT, or FULL OUTER JOIN).

#### 2. What  is the purpose of indexing in SQL? How does it improve query performance?
+ Indexes allow the database to find data faster by reducing the amount of data that needs to be scanned. They improve query performance by enabling faster retrieval of records, though they can slow down write operations e.g **INSERT, UPDATE, DELETE** due to the need to update the index.
+ The database uses an index as a shortcut rather than scanning each row to find records.

#### 3. Explain the difference between WHERE and HAVING clauses.
+ **WHERE** filters rows before any grouping is done, while HAVING is used to filter groups after the GROUP BY clause has been applied.

#### 4. How would you retrieve the second-highest salary from an Employee table?
+ There are several ways, one common approach is:-
```
SELECT MAX(salary)
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
```

#### 5. What is a **Subquery**?
+ A ***Subquery*** is a query nested inside another query.

#### 6. What is a __Primary Key__?
+ A __Primary Key__ is a unique identifier for a record in a table. It must contain unique values and cannot be ***NULL***.

#### 7. What is a __Foreign Key__?
+ A __Foreign Key__ is a column or a set of columns in one table that uniquely identifies a row in another table, creating a link between the two tables.

#### 8. What does the __SELECT__ statement do?
+ The __SELECT statement retrieves data from a database.

#### 9. How do you select all columns from a table?
~~~
SELECT * FROM table_name;
~~~

#### 10. How do you filter records in SQL?
+ You use the **WHERE** clause to filter records.
+ for example:-
```
SELECT * FROM table_name WHERE condition;
```

#### 11. How do you **Sort** records in SQL?
+ Use the **ORDER BY** clause to sort records.
+ for example:-
```
SELECT * FROM table_name ORDER BY column_name;
```

#### 12. What is the purpose of the **DISTINCT** keyword?
+ **DISTINCT** removes duplicate records from the result set.
+ for example:-
```
SELECT DISTINCT column_name FROM table_name;
```

#### 13. How do you find the number of rows in a table?
+ Use the ***COUNT*** function
```
SELECT COUNT(*) FROM table_name;
```

#### 14. What is a self-join and when would you use it?
+ A self-join is when a table is joined with itself, typically used to compare rows within the same table. This is useful in scenarios like finding employees who are managers of other employees within the same table.

#### 15. How do you perform a **LEFT JOIN**?
```
SELECT columns
FROM table1 LEFT JOIN table2
ON table1.column = table2.column;
```

#### 16. What is a **UNION** in SQL?
+ **UNION** combines the results of two or more SELECT queries and removes duplicates.

#### 17. What is the difference between **UNION** and **UNION ALL**?
+ **UNION** removes duplicates whereas **UNION ALL** includes all duplicates.

#### 18. How do you update existing records in a table?
+ Use the **UPDATE** statement
```
UPDATE table_name SET coulumn_name = value WHERE condition;
```

#### 19. How do you delete records from a table?
+ Use the **DELETE** statement
```
DELETE FROM table_name WHERE condition;
```

#### 20. How do you insert new records in a table?
+ Use the **INSERT INTO** statement
```
INSERT INTO table_name(column1, column2) VALUES(value1, value2);
```

#### 21. What is a **NULL** value in SQL?
+ **NULL** represents missing or unknown data in a table

#### 22. What is normalization?
+ ***Normalization*** organises data to reduce redundancy and improve data integrity.

#### 23. What are the common SQL data types?
+ Common data types include *INTEGER, VARCHAR, DATE, and FLOAT*

#### 24. What is the purpose of the **GROUP BY** clause?
+ **GROUP BY** is used to group rows that have the same values in specified columns into summary rows.

#### 25. What is a **WINDOW** function in SQL?
+ A **WINDOW** function performs calculations across a set of table rows that are related to the current row, without collapsing the result set. Examples include **ROW_NUMBER()**, **RANK()**, **SUM()**

#### 26. How does **PARTITION BY** clause work with **WINDOW** functions?
+ **PARTITION BY** clause divides the result set into partitions to which the window function is applied. Each partition is processed separately.

#### 27. What is the **ROW_NUMBER()** function used for?
+ **ROW_NUMBER()** assigns a unique sequential integer to rows within a partition of a result set. 
+ Example:
```
ROW_NUMBER() OVER (PARTITION BY column_name ORDER BY column_name)
```

#### 28. How does the **RANK()** function differ from the **DENSE_RANK()**?
+ **RANK()** assigns ranks with gaps in case of ties, whereas **DENSE_RANK()** assigns consecutive ranks without gaps for ties.

#### 29. What is a Common Table Expression (CTE)?
+ A **CTE** is a temporary result set defined within the execution scope of a single SQL statement. It simplifies complex queries and improves readability.

#### 30. How do you write a recursive **CTE**?
```
WITH RECURSIVE cte_name AS (SELECT_statement UNION ALL SELECT_statement FROM cte_name) SELECT * FROM cte_name;
```

#### 31. What is a cursor and when would you use it?
+ A *Cursor* is a database object that allows row-by-row processing of the result set. It's useful when operations need to be performed on each row individually.

#### 32. How do you handle transactions in SQL?
+ Transactions are handled with **BEGIN TRANSACTION, COMMIT** to save changes and **ROLLBACK** to restore the changes if there is an error.

#### 33. What is materialized view?
+  A materialized view is a precomputed table that stores the results of a query, which can improve performance for complex queries by avoiding repititive calculations.

#### 34. How does a clustered index differ from a non-clustered index?
+ A *clustered index* determines the physical order of data in a table, whereas a *non-clustered* index is a separate structure that points to the data's physical location.

#### 35. What is the purpose of **EXCEPT** clause?
+ **EXCEPT** returns distinct rows from the first SELECT statement that are not present in the second SELECT statement.

#### 36. What are ACID properties in SQL?
+ **ACID** stands for ***Atomicity, Consistency, Isolation, and Durability*** ensuring reliable transactiions in a database.

#### 37. How does a *non-clustered index* improve query performance?
+ A *non-clustered index* creates a separate structure from the table data that speeds up the retrieval by using a pointer to the actual data rows.

#### 38. What is denormalization and why is it used?
+ *Denormalization* involves combining tables to improve query performance and simplify complex queries, often used at the cost of data redundancy.

#### 39. What is a stored procedure and when is it used??
+ A *Stored procedure* is a precompiled collection of SQL statements that can be executed as a unit. It's used to encapsulate repetitive tasks and improve performance and security.

#### 40. What is a **Trigger** in SQL?
+ A **Trigger** is a set of actions that automatically execute in response to certain events on a table or view, such as **INSERT**, **UPDATE**, or **DELETE**.

#### 41. What is an **Index Seek** and **Index Scan**?
+ **Index seek** is a query operation that uses an index to find the exact rows, while **Index scan** is a query operation that reads the entire index to retrieve the data, which is less efficient.

#### 42. How do you handle complex joins in SQL?
+ Complex joins involve combining multiple tables using different join e.g. **INNER, LEFT, RIGHT, FULL** to fetch and analyze data from multiple tables.

#### 43. What are the advantages and disadvantages of *indexing*?
+ Indexing speeds up query performance but can slow down data modification operations e.g. **INSERT, UPDATE, DELETE** due to the need to update the index.

#### 44. What is a full-text search and how does it work?
+ **Full-text** search allows for sophisticated search capabilities within text columns by using special indexes to improve performance and relevance.

#### 45. How does SQL Server handle locking and concurrency?
+ SQL Server uses various isolation levels and locking strategies to manage access to data and prevent conflicts.

#### 46. What is the purpose of the **WITH (NOLOCK)** hint?
+ The **WITH (NOLOCK)** hint allows reading data without acquiring a lock, potentially improving performance but risking uncommited or inconsistent data.

#### 47. How do you optimize SQL queries for performance?
+ **Query Optimization** involves analyzing execution plana, creating appropriate indexes, avoiding unnecessary calculations, and reducing the complexity of joins and subqueries.

<center>THE END</center>

---