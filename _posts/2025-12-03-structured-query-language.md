---
tags: [database, sql, data]
---

Ranja Sarkar


Structured Query Language or SQL allows interaction with a database by writing queries to retrieve, manipulate, and manage data stored in the database tables. It is basically the language to communicate with data. 

# RDB

A relational database (RDB) uses SQL and its variants to access data. One can use SQL to create, read, update, and delete tables of data stored in the RDB.

Examples of RDBMS:

1. [MySQL](https://www.mysql.com/): It is an open-source RDBMS that is used for developing web applications, often accessed using PHP. It has been around since 1995 and has a large community. 

2. [Microsoft SQL Server](https://www.microsoft.com/en-in/sql-server/): It is a server-based RDBMS from Microsoft, typically used as a backend for applications running on a network. 
   
3. [PostgreSQL](https://www.postgresql.org/): It is an open-source RDBMS that emphasizes extensibility and compliance to the ANSI SQL standards. Postgres is also typically used for wenApp development.

4. [SQLite](https://www.sqlite.org/): It stores a database in a single file (.db). One of the most significant advantages with SQLite is that all data can be stored locally without having to connect the database to a server. It works seamlessly with python. 

[CodeAcademy](https://www.codecademy.com/catalog/language/sql) offers some excellent content and courses on SQL.

-----

There are non-relational databases as well,  called NoSQL databases. These are different from RDBs, like [MongoDB](https://www.codecademy.com/article/introduction-to-mongo-db-data) which is a document (unstructured data) database.  

Within an instance of MongoDB are collections. Collections are subsets of data. Assuming our database for example, database of a store selling cameras contains three types of data – sales, inventory, and customer info – each of these would have its own collection. Within each collection, we store individual records called documents. Every customer would have his/her own document within the collection. In summary, a document is simply a record that stores information about a particular entity. A collection is a group of documents containing similar information. Finally, a MongoDB database is a number of collections assembled together to store data for a specific use case,here that of the camera store. 

<img width="328" height="194" alt="mdb" src="https://github.com/user-attachments/assets/99ee73f1-45ae-4fa3-82be-d43f0c5900ac" />

-----

Many potential SQL users are also [pandas](https://pandas.pydata.org/) users. A [comparison of pandas with SQL](https://pandas.pydata.org/docs/getting_started/comparison/comparison_with_sql.html) only makes us realize that operations such as LIMIT, DISTINCT, GROUP BY, WHERE, HAVING, ORDER BY, JOIN are routine work of a data professional. 

SQL and pandas serve equally well for data exploration, the latter however is more than a query engine. One can export a pandas dataframe (df) to a multitude of formats which [includes SQL](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_sql.html).

<img width="214" height="38" alt="pd" src="https://github.com/user-attachments/assets/6c163851-56d9-4bc5-8712-ca9b42c963f9" />

# RDBMS

A **data warehouse** is a data management system that stores current and historical data from multiple sources in a business-friendly manner for insights and reporting. Data warehouses are typically used for data analysis, business intelligence (BI), reporting, and preparing data for machine learning (ML). 

<img width="105" height="244" alt="dwh" src="https://github.com/user-attachments/assets/d2090e7a-0810-43bf-9a53-5a190cb124a0" />

Data warehouses make it possible to easily analyze business data uploaded from operational (or transactional) systems such as point-of-sale systems, sales databases, inventory management systems. Data may pass through an operational data store and require data cleansing to ensure data quality before it can be used for reporting. Data is cleansed, transformed and integrated into a schema that is optimized for querying and analysis.

<img width="582" height="296" alt="dwh" src="https://github.com/user-attachments/assets/70757533-cc7b-4add-b21b-514539503be7" />

-----

A data lake is an unstructured or semi-structured data repository that allows for the storage of vast amounts of raw data in its original format. Data lakes are designed to ingest and store all types of data — structured, semi-structured or unstructured — without any predefined schema. Data is often stored in its native format and is not cleansed, transformed or integrated, making it easier to store and access large amounts of data

<img width="214" height="250" alt="dl" src="https://github.com/user-attachments/assets/15f33db1-38ac-4412-bcc4-f2277e5f6fba" />

-----


