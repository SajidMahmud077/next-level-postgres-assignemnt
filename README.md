1.What is a Schema in PostgreSQL?
=>In PostgreSQL, a schema is like a folder or namespace inside a database. It logically groups tables, views, functions, sequences, types, and other database objects.
schema helps you:
*Keep things organized
*Avoid name conflicts
*Manage access permissions better
A database schema is like the foundation of structure in a PostgreSQL database. Without schemas, large systems would become chaotic and hard to maintain. 
Mastering them allows you to build organized, secure, and scalable database solutions.A database schema is like the foundation of structure in a PostgreSQL database.
Without schemas, large systems would become chaotic and hard to maintain. Mastering them allows you to build organized, secure, and scalable database solutions.


2.Explain the Primary Key and Foreign Key concepts in PostgreSQL.
=>Primar and Foriegn key is concepts of postgresSQL.They help data organization
Primary Key?
=> 
*Primary key is a unique id of every row in table
*IT uniquly identified record
*It never remains empty
Example:
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT,
  email TEXT
);
What is a Foreign Key?
=> A foreign key is like a reference or link to a primary key in another table. It creates a relationship between tables by pointing to a unique record in the referenced table.
Example:
CREATE TABLE posts (
  id SERIAL PRIMARY KEY,
  user_id INTEGER REFERENCES users(id),  -- foreign key 
  content TEXT
);



3.What is the difference between the VARCHAR and CHAR data types?
=>CHAR 
*Fixed-length text.
*Always stores the exact number of characters you specify.
*If the text is shorter, it pads with spaces to fill the length.
*Use it when you know the exact length of data like country codes, fixed-length IDs.

Example:

CREATE TABLE countries (
  code CHAR(3) 
);

=> VARCHAR 
*Variable-length text.
*Stores text up to the specified length.
*No padding  only stores what you insert.
*Use it when data length can vary (like names, emails).

Example:

CREATE TABLE users (
  name VARCHAR(50) 
);



4.Explain the purpose of the WHERE clause in a SELECT statement.
=>The WHERE clause is like a filter — it helps you pick only the rows that match certain conditions when you query data.
Example:
SELECT * FROM users WHERE city = 'New York';
The WHERE clause supports all kinds of conditions, including:

Equality (=)
Inequality (!=, <>)
Greater or less than (>, <, >=, <=)
Pattern matching (LIKE)
Logical combinations (AND, OR)




5.How can you modify data using UPDATE statements?
=>The UPDATE statement in PostgreSQL allows you to change existing records (rows) in a table.
You can modify:
*One or multiple columns
*(One or many rows (using conditions)
*Even data in joined tables (with advanced queries)
Example:
UPDATE table_name
SET column1 = value1,
    column2 = value2,
    ...
WHERE condition;


