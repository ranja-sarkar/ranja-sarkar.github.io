---
tags: [database, sql, data]
---

Ranja Sarkar


Structured Query Language or SQL allows interaction with a database by writing queries to retrieve, manipulate, and manage data stored in the database tables. It is basically the language to communicate with data. A relational database management system (RDBMS) uses SQL and its variants to access data from a database. One can use SQL to create, read, update, and delete tables of data in RDB.

Examples of RDBMS:

1. [MySQL](https://www.mysql.com/): It is an open-source RDBMS that is used for developing web applications, often accessed using PHP. It has been around since 1995 and has a large community. 

2. [Microsoft SQL Server](https://www.microsoft.com/en-in/sql-server/): It is a server-based RDBMS from Microsoft, typically used as a backend for applications running on a network. 
   
3. [PostgreSQL](https://www.postgresql.org/): It is an open-source RDBMS that emphasizes extensibility and compliance to the ANSI SQL standards. Postgres is also typically used for wenApp development.

4. [SQLite](https://www.sqlite.org/): It stores a database in a single file (.db). One of the most significant advantages with SQLite is that all data can be stored locally without having to connect the database to a server. It works seamlessly with python. 

[CodeAcademy](https://www.codecademy.com/catalog/language/sql) offers some excellent content and courses on SQL.

There are non=relational databases as well,  called NoSQL databases. These are different from RDBs, like [MongoDB](https://www.codecademy.com/article/introduction-to-mongo-db-data) which is a document (unstructured data) database.  

Within an instance of MongoDB are collections. Collections are subsets of data. Assuming our database for example, database of a store selling cameras contains three types of data – sales, inventory, and customer info – each of these would have its own collection. Within each collection, we store individual records called documents. Every customer would have his/her own document within the collection. In summary, a document is simply a record that stores information about a particular entity. A collection is a group of documents containing similar information. Finally, a MongoDB database is a number of collections assembled together to store data for a specific use case,here that of the camera store. 

<img width="328" height="194" alt="mdb" src="https://github.com/user-attachments/assets/99ee73f1-45ae-4fa3-82be-d43f0c5900ac" />
