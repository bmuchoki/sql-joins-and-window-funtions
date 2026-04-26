# Joins
** Let's JOIN It! **
Joins combine two or more tables based on a related column.
They aid in:
- Retrieval of connected data that is stored across multiple tables.
- Matching records using columns.
- Improvement of Data Analysis through the combination of related information.
- Creation of a meaningful result set from separate tables.

## Types of SQL joins
SQL joins are categorized by how rows from two tables are matched and combined.
- ** SQL Inner Join: ** They retrieve rows where matching values exist in both tables.
They help in combining records based on a related column, retrieving only matching rows from both tables and ensuring accurate data relationships between tables.

*** Syntax ***
```Inner Join
SELECT table1.column1,table1.column2,table2.column1,.... FROM table1  INNER JOIN
 table2 ON  table1.matching_column = table2.matching_column;```
* The join is also known as the Inner Join. *
* For Instance, if I have two tables, the customers table and orders table, and I want to know the customer who made an order, I can use the common column, which is the customer_id, to merge the tables.*
** The Snapshot below shows a sample query: **

![INNER JOIN](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vv2oj2zuxx5zx1gezj5j.png)
** Left Join: ** They retrieve all rows on the left table and matching rows from the right table, and show null values where no match exists. It prioritizes the first table you mention.

*** Syntax ***
``` Left Join
SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
LEFT JOIN table2
ON table1.matching_column = table2.matching_column;```
* The Left Join is also known as the Left Outer Join. *
* For Instance, if I have two tables, the customers table and orders table, and I want to know the customer who made an order, I can use the common column, which is the customer_id, to merge the tables. The first table I chose is the customers table. *
** The Snapshot below shows a sample query: **

![LEFT JOIN](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ovq3erq8cdq69k75dklv.png)
** Right Join: ** It retrieves all rows from the right table and matching rows from the left table, and displays null values where no matching records exist in the left table. It prioritizes the second table you choose.
* The Right Join is also known as the Right Outer Join. *
*** Syntax ***
```Right Join
SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
RIGHT JOIN table2
ON table1.matching_column = table2.matching_column;```

* For Instance, if I have two tables, the customers table and orders table, and I want to know the customer who made an order, I can use the common column, which is the customer_id, to merge the tables. The first table I chose is the orders table. *
** The Snapshot below shows a sample query: **

![Right Join](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vmjh6pbuqbtlushzjht6.png)

** SQL Full Join: ** It combines the results of both the left and right joins, providing complete data from both sides of the join.
*** Syntax ***
```SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
FULL JOIN table2
ON table1.matching_column = table2.matching_column;```

* If a customer has never placed an order, they still show up. If an order has no matching customer, it still shows up. Nobody gets left out. *
** The Snapshot below shows a sample query: **

![Full Join](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fhurif9yts0mk98nx3yq.png)

# Window Functions in SQL
They perform calculations across a specific set of rows(the window)(defined by an over clause) that are related to the current row without collapsing them into a single value.
They use values from one or multiple rows to return a value for each row.
They are commonly used for tasks such as aggregation, averaging, ranking, and running totals.
** Key Components of SQL Window Functions **
- Select: This defines the columns you want to select from the table_name.
- Function: This is the window function you want to use.
- Over Clause: This defines the partitioning and ordering of rows and can be applied with functions to compute aggregated values.
- Partition by: This divides rows into partitions based on specified expressions. It is suitable for large datasets because it makes them simpler to manage.
- Order by: This is a specified order expression to define the order in which rows will be processed within each partition.
- Output column: This is the name you give to your output column.
*** Window functions are used after the processing of WHERE, GROUP BY and HAVING.

** Syntax **
```SELECT column_name1, 
       window_function(column_name2) 
       OVER ([PARTITION BY column_name3] [ORDER BY column_name4]) AS new_column
FROM table_name;```

** Types of SQL Windows Functions **
*** Aggregate Functions ***
- AVG: Average value in a group. It ignores null values.
- MAX: Finds the maximum value in an expression.
- MIN: Finds the minimum value in an expression.
- SUM: Sum of all values, or only the distinct values.
- COUNT: This is the number of times a value is found in a group.
- STDEV: Returns the statistical standard deviation of all values in the specified expression.
- STDEVP: Returns the statistical standard deviation for the population for all the values in the specified expression.
- VAR: Returns the statistical variance of all the values in the specified expression. An over clause may follow it.
- VARP: Returns the statistical variance for the population for all the values in the specified expression.

*** Ranking Window Functions. ***
- Row-Number: It assigns a unique number to each row in a result set. Increment is by 1 for every row, and avoids duplication.
- Rank: It assigns a unique rank to each row with gaps/or while skipping duplicates/ties in a result set. Mainly used to organize and analyze data.
- Dense Rank: It assigns a unique rank to each row without skipping rank numbers for duplicates. The same rank can have the same values or ties.
- Percent Rank: It shows the relative rank of a row as a percentage within a group of rows.
N-tile: It distributes rows in an ordered partition with a specified number of approximately equal groups.

*** Value Window Functions. ***
- LAG: Retrieves values from rows that precede the current row in the result set.
- LEAD: Retrieves values from rows that follow the current row in the result set.
- FIRST_VALUE: Returns the first value in an ordered set of values within a partition.
- LAST_VALUE: Returns the last value in an ordered set of values within a partition.
- NTH_VALUE: Returns the value of the nth row in the ordered set of values.
- CUME_DIST: Returns the cumulative distribution of a value in a group of values.

*** Benefits of SQL Window Functions ***
- Efficiency: There are fewer queries to be processed by the query. Queries are concise and precise.
- Versatility: They help in aggregation, ranking, distribution, etc., without narrowing the result set down to a single row.
- Row-Level Context: They preserve the original rows and columns in the result set.

*** To Note: ***
*Partition carefully because, without a partition, the whole table is treated as one group.*
*Check order by because it controls the calculation order in the window.*

### Conclusion
Data rarely comes neat and ready to use. Depending on your needs, joins and window functions are how you make sense of it; Connecting relationships and unearthing insights that would otherwise stay hidden. Knowing which tool to reach for makes all the difference. And like most things, the more you practice, the more natural it becomes.
