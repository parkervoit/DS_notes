# 3.22.2021

# Git

## Git is a great way to share and update code
try not to commit unless you have something substantial, like a code fix or a new function. You dont need to commit for every line of code
GIT PUSH EVERY DAY

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

# 3.23.2021

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

