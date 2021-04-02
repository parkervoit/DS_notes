# Git

## Git is a great way to share and update code
try not to commit unless you have something substantial, like a code fix or a new function. You dont need to commit for every line of code
GIT PUSH EVERY DAY!!!

### What is git?
- Git is a "distributed version control system"
- Git is a permanent record w/ a time machine (and parallel universe component)
- github is like dropbox for code
- we need to save our changes
- we need to save a record of what changed, when, and why
- we need the ability to travel in time to save points
- Version Control System (VCS) allow us to add lots of information and meta-data to our source code
- Pick up our fundamental git vocabulary
    - repo is short for repository
    - repository is a git enable folder
    - local means your computer your working on
    - remote means a remote computer where you're backing stuff up
    - diff means to show differences - what's new? what's removed?
    - "commit" means one or more changes to one or more files
    - commits are our save points.
    - commit messages are meta-data that explain each commit

### workflow
- do work until you've finished a thing or fixed a thing...
- do work, add lines to files, make new files, edit files, delete, whatever...
- `git status` to show which files changed
- `gid diff` to see what has changed in those files
- `git add filename` (where filename is an actual filename)
- run `git status` again to see that file show green
- Adding a file is like putting a letter in an envelope..
- `git commit` will open your editor so you can type the commit message
- save and close that editor window
- we can add one or more changes to each commit
- `git push` uploads any commits we have to your remotes
- lather, rinse, repeat...
- `git remote -v` shows all of your remotes
- `git branch -m main` changes your branch to the `main` branch
- `git config --global init.defaultBranch main` sets your git profile default branch to main rather than master

# SQL Notes
### vocab words
- CRUD: Create, Read, Update, Delete records
- SQL: Structured Queary Language
- RDBMS: Relational Database System
- structured data: data arranged into a database architecture
- unstructured data: messier data, although a more flexible data structure
- Data definition language (DDL): commands that change the structure of tables in the database
- Data manipulation language (DML): used to insert, update, delete, and retreive information from databases
### SQL flavors
- MS SQL server
- MySQL (free)
- Oracle
- PostGRES (free)
- SQLite (free), less bells and whistles, efficient. Used in apps for local DB storage
## SQL
- SQL is structured Data
    - structured data is arranged into databases
- NoSQL is for unstructured Data
    - MongoDB (Free) , stores "documents" instead of rows
    - Firebase from Google
    - Reddis
    - .json stores DB into dictionaries 
- SQL is great for managing massive databases, way more efficient than something like excel 
- We use a SQL client to connect to a SQL server that holds our database, then execute SQL commands in the client to manipulate the server
### Sequel Pro
- we will be using Sequel Pro which uses the MySQL dialect
- it connects to a shared cloud server with a few databases for practice
### Queries
- made up of statements and commands sent to the server, with results sent back to the client
- These statements and commands fall across DML and DDL categories
- You can chain queries to pull together multiple datasets
## MySQL Databases
### DB commands
- `SHOW DATABASES;` to see a full list of DBs in the MySQL server
    - this will output a list of database names
    - sequel pro has a drop down menu that lists all the databases
- `USE database_name;` lets you select and use a database on the server
- `database_name.table_name` lets you query tables or objects in a seprate database
- `SELECT database();` shows which database you have currently selected
- `SHOW CREATE DATABASE database_name;` lets you create a database
    - words like `SELECT`, `INSERT`, and `CREATE` are reserved words and cannot be used for names
## MySQL Tables
### Data Types
- Numeric Types:
    - `INT`: any number without a decimal point. Can be `UNSIGNED` which means it can only hold positive values
    - `FLOAT`: A number with decimal values, can be less accurate. Use `DOUBLE` to increase precision
    - `DECIMAL(length, precision)`: A precise decimal number. Must be defined with a length(# of digits stored in the value) and precision(# of digits after the decimal) arguments. Perfect for storing monetary values
- MySQL has no native support for boolean values
    - Uses `TINYINT` with a range of -128 to 127. Treats 0==False and 1==True
- String Types:
    - `CHAR(length)`: a string with a fixed # of chars where length can be from 1 to 255. 
        - If a string shorter than length is stored, it is filled with empty space to take up the full size.
        - if it is larger than length, it will return an error
        - Useful for storing values with consistent length 
    - `VARCHAR(length)`: for strings where the length can vary up to a max number
    - `TEXT`: A large block of characters that can be any length. Only use for very large blocks of text, like the full text of an article.
- Date Types:
    - `DATE`: a date value without any time. Displayed `YYYY-MM-DD`
    - `TIME`: Time down to seconds. Uses a 24 hr system
    - `DATETIME`: Shows both time and date. Displayed `YYYY-MM-DD HH:MM:SS` 
- `NULL`: not 0, instead the absence of any value. Using `NOT NULL` helps prevent any SQL weirdness that may arise from the database

### Creating Tables
- General syntax
CREATE TABLE table_name (
    column1_name data_type,
    column2_name data_type,
    ...
);
#### Primary Keys
- Primary keys are a way to uniquely identify a single row in a table
- its a column with the following rules
    1. Each value must be unique (think IDs or SS#)
    2. Cannot be `NULL` 
    3. Only one per table
### Showing Tables
- `SHOW TABLES;`: shows tables defined in the database
- `DESCRIBE table_name;` or `SHOW CREATE` or `EXPLAIN` to find more info out about the table. 
## Basic Statements
- SQL encloses strings with (') as a standard
### Comments
- '#' or -- for single line comments 
- /* and */ for multi line comments
### Select Statement
- `SELECT column1 [, column2[, ...]] FROM table_name;` finds and returns rows from a given column or columns in a table. 
- `SELECT * FROM table_name;` shows all available columns from a table 
- `SELECT DISTINCT column1 FROM table_name;` eliminates duplicate values from a select output
    - adding `WHERE column_name = 'value';` specifies a condition that must be true for a given row to be returned
    - you can use operators as part of a `WHERE` clause
- `SELECT 'string' AS column_name;` provides an alias for an arbitrary string as an output.
-`SELECT 1+1 AS two`: A convenient way to rename tables, columns or other outputs temporarily 
### WHERE in depth
- `WHERE` indicates a condition that needs to be satisfied to show a row
- Combining with `LIKE` will search for similarities
- Use `%` to search for strings that contain a specified letter combination
- `BETWEEN value1 AND value 2` is how you specify a range 
-  `IN ('val1','val2','val3')` queries only those specific sets of values. 
- Can use comparison operators `=`,`<`,`<=`
- Can use `IS NULL` or `IS NOT NULL` to see if a value is null
- Can use `AND` and `OR` operators to string together `WHERE` clauses
- `NOT` will show a value if the condition is not true
### ORDER BY
- `ORDER BY` lets us specify the order in which we view data
- Generalized syntax:`SELECT column FROM table ORDER BY column [ASC|DESC];`
- Columns selected can be aliases, names, or positions. Positions begin at 1.
- `ORDER BY` can be used with any `SELECT` queries
- you can chain `ORDER BY` arguments by seperating with a `,`
### LIMIT 
- `LIMIT` lets you limit results returned to a specified number or range
- Generalized syntax: `SELECT columns FROM table LIMIT count [OFFSET count];`
- `LIMIT` specifies a certain amount of rows to return, and `OFFSET` sets the row to start counting from
- these two commands are typically used for creating pages of data
## GROUP BY
- `GROUP BY` syntax : `SELECT column FROM table GROUP BY column_name [ASC|DESC];`
    - returns only unique occurances in the column, functionally similar to `DISTINCT`
- Any columns in the `SELECT` statement must be in the `GROUP BY` clause
## Aggregate Functions
- Aggregate functions works with data across all rows in a result, rather than in a single column or two. 
- `COUNT(*)` returns the number of non-null expressions in a result
- `AVG()` returns the average value of a result
- `MAX()` and `MIN()` returns the max and min of a result, respectively
- `STD()` or `STDDEV()` returns the standard deviation
- `SUM()` returns the sum 
### USING GROUP BY with Aggregate Functions
- Aggregates with GROUP BYs can be used to find deeper insights into the data
## Relationships
- MySQL is an RDBMS, and the R stands for relational. MySQL can use this structure to combine and manage data from different tables
### Indices
- Primary Keys: a unique identifying index that keeps columns related to rows
    - it will typically be some sort of user_ID or other unique identifier like a DL##
- Unique indexes: similar in function as a primary key, but unlike primary keys, you can have more than one unique index per table. 
    - You can use `ALTER TABLE 'tablename' ADD UNIQUE (UNI_ID)` to add a unique key. 
- Foreign Keys: keys used to relate tables used in joins. 
- Multiple-Column Indexes: you can make composite indexes to further specify what you want returned
    - e.g. use `UNIQUE(first_name, last_name);` to make a unique column of first and last name combinations
### JOIN
- There are 3 types of joins:
    1. `JOIN` (a.k.a INNER JOIN) 
        - joins two tables at one key, only includes not-null rows and values that are shared by both tables
    2. `LEFT JOIN`
        - joins all of table 1, while only returning shared from table 2. 
    3. `RIGHT JOIN`
        - joins only shared values in table 1, while sharing all of table 2
-  `JOIN` syntax: `SELECT columns FROM table_a as A JOIN table_b as B ON A.id = B.fk_id;`
- If you want to join two tables and their keys have the same name you can use `USING(key_name)` instead of the ON statement.
### Sub-queries
- Also called nested queries, are queries within a query
- we want to use subqueries when we want to find out if a value is whithin a subset of acceptable values
- nested query syntax: `SELECT column_a, column_b, column_c FROM table_a WHERE column_a IN (SELECT column_a FROM table_b WHERE column_b = true);`
- Make sure the nested query runs on its own and selects the specified data you want. The outside query will operate using the nested query as a parameter. It's almost like a working table... although that language isnt the best. 
## Temporary Tables
* WARNING : the `DROP` commands and `ALTER` commands permanently change a table. For this reason, only do this on temporary tables, not on production database tables. 
- Temporary table name syntax: `CREATE TEMPORARY TABLE table_name(...);`
    - syntax is similar to creating regular tables, it just contains the `TEMPORARY` keyword
- You can insert values into a table using `INSERT INTO table_name(column) VALUES (1) , (2) , (3);` 
- Modify values using `UPDATE table_name SET column = column + 1;`
- Remove records with `DELETE FROM table_name WHERE column <> 2;`
- You can create a temp table using results from a query using `CREATE TEMPORARY TABLE table_name AS ('QUERY');`
- Use `ALTER TABLE table_name DROP COLUMN column_name` to delete a column
- Use `ALTER TABLE table_name ADD column_name data_type();` to add a column. 
- populate with `UPDATE`