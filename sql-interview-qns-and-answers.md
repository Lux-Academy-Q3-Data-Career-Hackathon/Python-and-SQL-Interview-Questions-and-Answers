SQL INTERVIEW QUESTIONS:

1. What is the difference between INNER JOIN and OUTER JOIN in SQL?
#INNER JOIN returns only the rows that have matching values in both tables. OUTER JOIN returns all the rows from one table
and the matching rows from the other table (can be LEFT, RIGHT, or FULL OUTER JOIN).
2. What  is the purpose of indexing in SQL? How does it improve query performance?
#Indexes allow the database to find data faster by reducing the amount of data that needs to be scanned. They improve
query performance by enabling faster retrieval of records, though they can slow down write operations (insertions, updates, and deletions)
due to the need to update the index.
3. Explain the difference between WHERE and HAVING clauses.
#WHERE filters rows before any grouping is done, while HAVING is used to filter groups after the GROUP BY clause has been
applied.
4. How would you retrieve the second-highest salary from an Employee table?
#There are several ways, one common approach:
sql
Copy code
SELECT MAX(salary)
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
5. What is a self-join and when would you use it?
#A self-join is when a table is joined with itself, typically used to compare rows within the same table. This is useful in
scenarios like finding employees who are managers of other employees within the same table.
