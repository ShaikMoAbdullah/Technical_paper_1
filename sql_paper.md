# SQL SELECT queries (Follow Along)

## Table of Contents
* Installing PostgreSQL
* Basics of SQL
* SELECT queries
* References
<br />

## 1. Installing PostgreSQL
To install PostgreSQL, first refresh your server’s local package index:
```
$ sudo apt update
```
Then, install the Postgres package along with a -contrib package that adds some additional utilities and functionality:
```
$ sudo apt install postgresql postgresql-contrib
```
Lets switch to postgres account:
```
$ sudo -i -u postgres
```
Then you can access the Postgres prompt by typing:
```
$ psql
```
This will log you into the PostgreSQL prompt, and from here you are free to interact with the database management system right away.

To exit out of the PostgreSQL prompt, run the following:
```
postgres=# \q
```
This will bring you back to the postgres Linux command prompt. To return to your regular system user, run the 'exit' command:
```
postgres@server:~$ exit
```
<br />

## 2. Basics of SQL 

### A. **Database**:
A database is an **organized collectionof data**, typically stored **electronically** in a **computer system**. A database is usually controlled by a **database management system (DBMS)**. Ok, Now what is DBMS. Let's have a look at that.

### B. **DBMS**(Database management system)
It is a software for **storing** and **retrieving** users data while considering appropriate security measures.

Ok, So we understood that DBMS is used to operate on the Database. So, what does SQL have to do with this.

### C. **SQL**(Structured Query Language)
SQL is a **database computer language** designed for the **retrieval** and **management** of data in a relational database.

Now, that the terms have been cleared, We shall get started with SQL. 

>There are many **popular SQL databases** including **SQLite**, **MySQL**, **Postgres**, **Oracle** and **Microsoft SQL Server**. All of them support the *common SQL language standard*, which is what this article will be all about, but each implementation can differ in the additional features and storage types it supports. Don't worry, Just follow along.

## 3. SELECT queries

Let's have a look at how the Relational database actually look like. 

### Table: Movies

Id	| Title	| Director	| Year	| Length_minutes
----|-------|-----------|-------|---------------- 
1 |	Toy Story |	John Lasseter |	1995 |	81
2 |	A Bug's Life |	John Lasseter |	1998 |	95
3 |	Toy Story 2 |	John Lasseter |	1999 | 93
4 |	Monsters, Inc. |	Pete Docter |	2001 |	92
5 |	Finding Nemo |	Andrew Stanton |	2003 |	107
6 |	The Incredibles |	Brad Bird |	2004 |	116
7 |	Cars |	John Lasseter |	2006 |	117
8 | Ratatouille |	Brad Bird |	2007 |	115
9 |	WALL-E |	Andrew Stanton |	2008 |	104
10 |	Up |	Pete Docter |	2009 |	101

As we can see, Each of the tables are similar to an Excel spreadsheet, with a fixed number of named columns (the attributes or properties of the table) and any number of rows of data.

Let's start with the first query. 
>queries are nothing but statements
### 1. SELECT query
To retrieve data from a SQL database, we need to write SELECT statements. The query  declares what data we are looking for, where to find it in the database, and optionally, how to transform it before it is returned.

>**Table** in SQL represents an **entity** (e.g. movies), and each **row** in that table as a specific **instance** of that type(e.g 1, 2). This means that the **columns** would then represent the **common properties** shared by all instances of that entity(e.g. title, Year, etc).

Syntax:
```
SELECT column, another_column, …
FROM mytable;
```

Let's select some columns with all the rows.
```
SELECT * FROM movies;
```
And, you have got the output to be:
```
 id |      title      |    director    | year | length_minutes 
----+-----------------+----------------+------+----------------
  1 | Toy Story       | John Lasseter  | 1995 |             81
  2 | A Bugs Life     | John Lasseter  | 1998 |             95
  3 | Toy Story 2     | John Lasseter  | 1999 |             93
  4 | Monsters, Inc.  | Pete Docter    | 2001 |             92
  5 | Finding Nemo    | Andrew Stanton | 2003 |            107
  6 | The Incredibles | Brad Bird      | 2004 |            116
  7 | Cars            | John Lasseter  | 2006 |            117
  8 | Ratatouille     | Brad Bird      | 2007 |            115
  9 | WALL-E          | Andrew Stanton | 2008 |            104
 10 | Up              | Pete Docter    | 2009 |            101
(10 rows)
```
'*' represents 'all rows'. The output is representing all rows matching the following pattern.

You can also find a specific column of the table. If we want to know the name of all the movies only.
```
SELECT title FROM movies;
```
You get the output as:
```
      title      
-----------------
 Toy Story
 A Bugs Life
 Toy Story 2
 Monsters, Inc.
 Finding Nemo
 The Incredibles
 Cars
 Ratatouille
 WALL-E
 Up
(10 rows)
```

Now, lets add some condition to the queries like:

Syntax:
```
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
```
```
SELECT title FROM movies WHERE Year=1999;
```
We get the output as:
```
    title    
-------------
 Toy Story 2
(1 row)
```
This tells us that 'Toy Story 2' had been released in the year 1999.

You can use the following operator in the WHERE clause to filter out results:
>- =, !=, < <=, >, >=	--> Standard numerical operators
>- BETWEEN … AND …	--> Number is within range of two values (inclusive)
>- NOT BETWEEN … AND …	--> Number is not within range of two values (inclusive)
>- IN (…)	--> Number exists in a list
>- NOT IN (…)	--> Number does not exist in a list

Now, lets filter out even more with the DISTINCT, ORDER BY, LIMIT, OFFSET.
```
SELECT DISTINCT Director FROM movies;
```
You get the output with the distinct directors of all the movies.
```
    director    
----------------
 Brad Bird
 John Lasseter
 Andrew Stanton
 Pete Docter
(4 rows)
```
Next, We would want to display movies released after 2000 and we used "ORDER BY col_name ASC/DESC" clause to present them in an ascending order. 
```
SELECT title, Year FROM movies
WHERE Year > 2000
ORDER BY Year;
```
You get the output as of movies released after 2000 and sorted in ascending order.
```
      title      | year 
-----------------+------
 Monsters, Inc.  | 2001
 Finding Nemo    | 2003
 The Incredibles | 2004
 Cars            | 2006
 Ratatouille     | 2007
 WALL-E          | 2008
 Up              | 2009
(7 rows)
```
Next, We would want to display 2 movies whuch had released after 2000, but from the second position. Limit clause gives the number of rows to print and OFFSET clause gives at which row to start in the table.
```
SELECT title, Year
FROM movies
WHERE Year > 2000
ORDER BY Year
LIMIT 2 OFFSET 2;
```
Now, there is a possibility of NULL values in databases.

Syntax is:
```
SELECT column, another_column, …
FROM mytable
WHERE column IS/IS NOT NULL
AND/OR another_condition
AND/OR …;
```
Now, lets write a query to find out if there are any NULL values in PostgreSQL.
```
SELECT * FROM movies WHERE title IS NOT NULL;
```
I get all the rows as output as there are no NULL values in the table.
```
 id |      title      |    director    | year | length_minutes 
----+-----------------+----------------+------+----------------
  1 | Toy Story       | John Lasseter  | 1995 |             81
  2 | A Bugs Life     | John Lasseter  | 1998 |             95
  3 | Toy Story 2     | John Lasseter  | 1999 |             93
  4 | Monsters, Inc.  | Pete Docter    | 2001 |             92
  5 | Finding Nemo    | Andrew Stanton | 2003 |            107
  6 | The Incredibles | Brad Bird      | 2004 |            116
  7 | Cars            | John Lasseter  | 2006 |            117
  8 | Ratatouille     | Brad Bird      | 2007 |            115
  9 | WALL-E          | Andrew Stanton | 2008 |            104
 10 | Up              | Pete Docter    | 2009 |            101
(10 rows)
```
So, This was about the basics of SQL. This should help you in giving you the foundation to dive into the domainof Database management system. I will be putting some links in the **Resources** section. Have a look at these pages in order to dive deep into SQL. 

## 4. Resources
- [Introduction to SQL](https://sqlbolt.com/lesson/introduction)
- [How to install postgreSQL in Ubuntu/MAC](https://www.digitalocean.com/community/tutorials/how-to-install-postgresql-on-ubuntu-20-04-quickstart)
- [How to Install and configuration PostgreSQL on Ubuntu Linux](https://youtu.be/-LwI4HMR_Eg)
- [Creating your first database](https://youtu.be/xaWlS9HtWYw)