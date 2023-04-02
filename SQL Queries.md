1. Make a copy of the table
2. Convert Data Types for each column if needed
3. Check that columns match the range/length that they should be.
4. Clean data

-   [SQL functions](https://www.w3schools.com/sql/sql_ref_sqlserver.asp "This link takes you to the W3 Schools SQL reference page for SQL functions."): A comprehensive list of functions.
-   [SQL Keywords](https://www.w3schools.com/sql/sql_ref_keywords.asp "This link takes you to the W3 Schools reference page for SQL keywords."): A helpful SQL keywords reference.

SELECT - Secifies what data we want to interact with in a table.
	SELECT (columns)
SELECT * - Used to interact with all of the data in a table.

FROM - Can pull from any table in the database.
	FROM (database.table)

INSERT INTO - To insert new data into a table.
	INSERT INTO (dataset.table)
		((columns we are adding to))
	VALUES - what values to insert into the table
	Ex: 
		INSERT INTO customer_data.customer_address
			(customer_id, address, city, state, zipcode, country)
		VALUES
			(2645, '333 SQL Road', 'Jackson', 'MI', 49202, 'US')

UPDATE - To update a data point
	UPDATE (dataset.table)
	SET (value to change) = (what to change it to)
	WHERE (where we are making the change) = (what is there now)
	Ex:
		UPDATE customer_data.customer_address
		SET address = '123 New Address'
		WHERE customer_id = 2645

New created tables will need to be saved to be kept.
DROP TABLE IF EXISTS - To clean up if you are creating new tables

## Cleaning Data in SQL 
-Check the data description for each column and then check to see if the columns all match the range/length that they should be.

DISTINCT - To make sure our results do not have duplicates
	SELECT
		DISTINCT (column)
	FROM
		(dataset.table)

Cleaning Text Strings before analyzing
		LENGTH (LEN) - To double check that string variables are consistent.
			SELECT
				LENGTH(column) AS (label the new column)
			FROM
				(dataset.table)
	Then, to see which ones are not the same number of characters in the text string:
		SELECT
			(column)
		FROM
			(dataset.table)
		WHERE
			LENGTH((column)) > (number it should be)
	FIx this using the Sub String Query
		SELECT
			DISTINCT (column)
		FROM
			(dataset.table)
		WHERE
			SUBSTR((column, What letter to start with, how many letters including this letter to pull)) = 'What we want it to be'
					Ex: SUBSTR(country, 1, 2) = 'US'

Removing extra spaces
	Checking that the characters are consistent
		SELECT 
			(column)
		FROM
			(dataset.table)
		WHERE
			LENGTH((column)) > (what it should be)
	If the extra character is an extra space
		SELECT 
			DISTINCT (column of the data we now want)
		FROM
			(dataset.table)
		WHERE
			TRIM((column we want to remove spaces from)) = '(which specific items in the column)'
	Ex:
		SELECT 
			state
		FROM
			customer_data.customer_address
		WHERE
			LENGTH(state) > 2
	If the extra character is an extra space
		SELECT 
			DISTINCT customer_id
		FROM
			customer_data.customer_address
		WHERE
			TRIM(state) = 'OH'

Missing Data - NULL
	Find Missing Data
		SELECT   
			* 
		FROM   
			(dataset.table)
		WHERE 
			(column we are looking at) IS NULL;
	Fill in Missing Data
		UPDATE   
			(dataset.table) 
		SET   
			(column) = "(what the value added is)" 
		WHERE   
			(column1 name) = "(value of the column for that row)"   
			AND (column2 name) = "(value of the column for that row)"   
			AND (column3 name) = "(value of the column for that row)"   ;
	Double check by searching to find missing data again

Identifying Potential Errors
	SELECT   
		DISTINCT (column)
	FROM   
		(dataset.table) ;
	-See if you find any errors

Correct Misspelled cells
		UPDATE   
			(dataset.table)
		 SET   
			 column = "(what it should say in the cell)" 
		WHERE   
			column = "(what it says in the cell now)" ;
	Check that it worked
		SELECT  
			DISTINCT (column) 
		FROM   
			(dataset.table);

Checking that a column values are in the correct range
	SELECT   
		MIN(column) AS (column),
		MAX(column) AS (column) 
	FROM   
		(dataset.table);

Counting rows to delete - After checking if there are values that are wrong in the table.
	SELECT
		COUNT(*) AS num_of_rows_to_delete
	FROM
		(dataset.table)
	WHERE
		(column) = (the value was that was wrong in the column);
Delete the row
	DELETE (dataset.table)
	WHERE (column) = (the value was that was wrong in the column);

COUNT - A query that returns the number of rows in a specified range.
		SELECT (column.table)
		COUNT(value in a column)
	COUNT DISTINCT - A query that only returns the distinct values in a specified range.
		SELECT(column.table)
		COUNT(DISTINCT (value in a column))
	-Both are for "How many...?" questions.

Ensure Consistency - Looking for Inconsistencies column by column
		SELECT
			DISTINCT (column)
		FROM   
			(dataset.table);
	Check LENGTH
		SELECT   
			DISTINCT (column),   LENGTH((column)) AS string_length 
		FROM   
			(dataset.table);
	TRIM extra spaces
		UPDATE
			(dataset.table)
		SET
			 (column) = TRIM((column))
		WHERE TRUE;
	Double check your work
		SELECT   
			DISTINCT (column) 
		FROM   
			(dataset.table);

## Formatting Data
Formatting
	CAST() - Can be used to convert anything from one data type to another.
		SELECT
			(column)
		FROM
			(dataset.table)
		ORDER BY
			(column) DESC
	Go to the table and look at the Schema to see what data type the database thinks a column is.
		SELECT
			CAST((column) AS (type we want to change it to and bit system))
		FROM
			(dataset.table)
		ORDER BY
			CAST((column AS (type we want to change it to and bit system)) DESC
	CONCAT() - Adds strings together to create new text strings that can be used as unique keys.
		SELECT
			CONCAT((column1, column2)) AS (new column name)
		FROM
			(dataset.table)
		WHERE
			column = '(what we are looking at in the column)'
		-Can be used as just: CONCAT((column1, column2))
		-To add a space: CONCAT((column1, ' ', column2))
		-Add ' ' around the word if using a string instead of a column
	CONCAT_WS - adds two or more strings together with a seperator
		=CONCAT_WS(‘ . ’, ‘www’, ‘google’, ‘com’)
		-The separator (being the period) gets input before and after Google when you run the SQL function
	CONCAT with + - Adds two or more strings together using the + operator
		‘Google’ + ‘.com’
	COALESCE() - Can be used to return non-null values in a list.
		SELECT
			COALESCE((which column to check first, which column to check second)) AS (new column name)
		FROM
			(dataset.table)
	LIMIT - Used to only get the top of what you are looking or
		LIMIT (number of rows you want)
	GROUP BY - A command that groups rows that have the same values from a table into summary rows.

CASE Statement - The CASE statement goes through one or more conditions and returns a value as soon as a condition is met. Can add IF/THEN.
	SELECT 
		(column associated with the problem)
		CASE
			WHEN (column that the problem is in) = '(What the cell says that's wrong)' THEN '(What the cell should say)'
			ELSE (column that the problem is in)
			END AS cleaned_(what was cleaned)
	FROM
		(dataset.table)
	[**SQL CASE**](https://www.w3schools.com/sql/sql_case.asp "This link takes you to a W3 Schools tutorial on the SQL CASE statement.")

HAVING - Allows you to add a filter to your query instead of the underlying table that can only be used with aggregate functions.
	[**SQL HAVING**](http://www-db.deis.unibo.it/courses/TW/DOCS/w3schools/sql/sql_having.asp.html "This link takes you to the W3 Schools tutorial on the SQL HAVING clause.")

JOIN - A SQL clause that is used to combine rows from two or more tables based on a related column. JOIN uses keys (primary and foreign) to identify relationships and corresponding values.
	INNER JOIN - A function that returns records with matching values in both tables.
	LEFT JOIN - A function that returns records from the left table and only the matching records from the right table.
	RIGHT JOIN - A function that returns records from the right table and only the matching records from the left table.
	fR JOIN - A function that combines RIGHT and LEFT JOIN to return all matching records in both tables.
		If there is a record in one table without a match in the other table it will create a null value.
	**ON** in SQL identifies how the tables are to be matched for the correct information to be combined from both.
		SELECT (table.column1, table.column2)
		FROM (table1)
		INNER JOIN (table2)
		ON (table1.column, table2.column)
	[**SQL JOINs**](https://www.w3schools.com/sql/sql_join.asp "This link takes you to a W3 Schools tutorial on SQL JOINs.")
![[JOIN - SQL.png]]

## Common Conversions
[Conversion Rules in Standard SQL](https://cloud.google.com/bigquery/docs/reference/standard-sql/conversion_rules "This link takes you to the Google Cloud BigQuery documentation on SQL.")
	CAST(expression AS typename)
	Converting a number to a string
		SELECT 
		CAST((numeric identified by the variable) AS STRING)
		FROM (table)
	Converting a string to a number
		SELECT
		CAST((string identified by the variable) AS INT)
		FROM (table)
	Converting a date to a string
		SELECT
		CAST((date identified by the variable) AS STRING)
		FROM (table)
	Converting a date to a datetime
		SELECT
		CAST((date identified by the variable) AS DATETIME)
		FROM (table)
	SAFE_CAST function - returns a value of Null instead of an error when a query fails.
		SELECT
		SAFE_CAST((date identified by the variable) AS STRING)
		FROM (table)
	More
		[CAST and CONVERT](https://docs.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql?view=sql-server-ver15 "This link takes you to Microsoft SQL Server documentation for CAST and CONVERT."): SQL Server reference documentation
	    [MySQL CAST Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html "This link takes you to MySQL reference documentation for CAST functions."): MySQL reference documentation
	    [How to: SQL Type Casting](https://www.blendo.co/blog/how-to-sql-type-casting/ "This link takes you to a blog on type casting in SQL."): Blog about type casting that has links to other SQL short guides

**Aliases** are used in SQL queries to create temporary names for a column or table.
	**Aliasing** is the process of using aliases.
		Aliasing a table
			SELECT column_name(s)
			FROM table_name AS alias_name;
		Aliasing a column
			SELECT column_name AS alias_name
			FROM table_name;
	If using AS results in an error when running a query because the SQL database you are working with doesn't support it, you can leave it out.

Subquery - A SQL query that is nested inside a larger query.
	The statement containing the subquery is called the Outer Query or Outer Select.
	The subquery is also called the Inner Query or Inner Select.
		The inner most query executes first.
	Subqueries must be enclosd within parentheses.
	[**Writing subqueries in SQL**](https://mode.com/sql-tutorial/sql-sub-queries/ "This link takes you to a Mode SQL tutorial on writing subqueries.")
	Ex: 
		SELECT (column1, column2)
			(SELECT
				AVG(column2)
			FROM (database.dataset.table)) AS (what to call this new column)
		FROM (database.dataset.table)

Adding column values together
	SELECT
		columnA,
		columnB,
		columnC,
		(column A + column B) * columnC AS columnx
	FROM
		table_name

Percentages
	Error fix
		WHERE
			column <> 0
	OR
		WHERE
			column != 0

Temporary Table - A database table that is created and exists temporarity on a databse server.
	https://www.coursera.org/learn/analyze-data/supplement/oGADZ/working-with-temporary-tables
		[Introduction to Temporary Tables in SQL Server](https://codingsight.com/introduction-to-temporary-tables-in-sql-server/ "This link takes you to an article that describes how to create a temporary table in SQL Server.")
		[SQL Server Temporary Tables](https://www.sqlservertutorial.net/sql-server-basics/sql-server-temporary-tables/ "This link takes you to a tutorial on how to create temporary tables in SQL Server.")
	SELECT INTO - copies data from one table into a new table, but doesn’t add the new table to the database. It’s useful if you want to make a copy of a table with a specific condition.
		Ex:
			SELECT *
			INTO AfricaSales
			FROM GlobalSales
			WHERE Region = "Africa"
	CREATE TABLE - is a good option when several people need to access the same temp table. This statement adds the table into the database.
		Ex:
			CREATE TABLE AfricaSales AS
			(
			SELECT *
			FROM GlobalSales
			WHERE Region = "Africa"
			)
	 WITH - is a type of temporary table that you can query from multiple times.
		The WITH clause approximates a temporary table.
		Ex:
			WITH trips_over_1_hr AS (
				SELECT *
				FROM
					bigquery-public-data.new_york.citibike_trips
				WHERE
					tripduration >= 60
						)
				##Count how many trips are 60+ mins long
				SELECT
					COUNT(*) AS cnt


