---
tags: [database, sql, data warehouse]
---


![fl1](https://github.com/user-attachments/assets/70fdb8bc-68d0-4851-be40-b20f7c456520)

<ins>**Querying Databases**</ins>

Structured Query Language or SQL allows interaction with a database by writing queries to retrieve, manipulate, and manage data stored in the database tables. It is basically the language to communicate with data. 

# RDBs or SQL Databases

A relational database (RDB) uses SQL and its variants to access data. One can use SQL to create, read, update, and delete tables of data stored in the RDB. These are the so-called CRUD operations - [create is DDL and update & delete are DML](https://milvus.io/ai-quick-reference/what-is-the-difference-between-ddl-and-dml-in-sql).

Examples of RDB management system (RDBMS):

1. [MySQL](https://www.mysql.com/): It is an open-source RDBMS that is used for developing web applications, often accessed using PHP. It has been around since 1995 and has a large community. 

2. [Microsoft SQL Server](https://www.microsoft.com/en-in/sql-server/): It is a server-based RDBMS from Microsoft, typically used as a backend for applications running on a network. 
   
3. [PostgreSQL](https://www.postgresql.org/): It is an open-source RDBMS that emphasizes extensibility and compliance to the ANSI SQL standards. Postgres is typically used for webApp development.

4. [SQLite](https://www.sqlite.org/): It stores a database in a single file (.db). One of the most significant advantages with SQLite is that all data can be stored locally without having to connect the database to a server. It works seamlessly with python. 

[CodeAcademy](https://www.codecademy.com/catalog/language/sql) offers some excellent content and courses on SQL.


# NoSQL Databases

There are non-relational databases as well,  called NoSQL databases. These are different from RDBs, like [MongoDB](https://www.codecademy.com/article/introduction-to-mongo-db-data) which is a document (unstructured data) database.  

Within an instance of MongoDB are collections. Collections are subsets of data. Assuming our database for example, database of a store selling cameras contains three types of data – sales, inventory, and customer info – each of these would have its own collection. Within each collection, we store individual records called documents. Every customer would have his/her own document within the collection. In summary, a document is simply a record that stores information about a particular entity. A collection is a group of documents containing similar information. Finally, a MongoDB database is a number of collections assembled together to store data for a specific use case,here that of the camera store. 

<img width="328" height="194" alt="mdb" src="https://github.com/user-attachments/assets/99ee73f1-45ae-4fa3-82be-d43f0c5900ac" />

Google Cloud provides BigTable as a NoSQL database.

<img width="457" height="86" alt="nosql" src="https://github.com/user-attachments/assets/b234d8d1-9f23-4af4-8f2d-31e8d02eda56" />

Azure CosmosDB is another non-relational database by Microsoft, designed for high-performance and low-latency applications.

# Data Warehouse

A **data warehouse** is a data management system that stores current and historical data from multiple sources in a business-friendly manner for insights and reporting. Data warehouses are typically used for data analysis, business intelligence (BI), reporting, and preparing data for machine learning (ML). 

<img width="105" height="244" alt="dwh" src="https://github.com/user-attachments/assets/d2090e7a-0810-43bf-9a53-5a190cb124a0" />

Data warehouses make it possible to easily analyze business data uploaded from operational (or transactional) systems such as point-of-sale systems, sales databases, inventory management systems. Data may pass through an operational data store and require data cleansing to ensure data quality before it can be used for reporting. Data is cleansed, transformed and integrated into a schema that is optimized for querying and analysis.

-----

A **data lake** is an unstructured or semi-structured data repository that allows for the storage of vast amounts of (raw) data in its original form. Data lakes are designed to ingest and store all types of data — structured, semi-structured or unstructured, without any predefined schema. 

<img width="214" height="250" alt="dl" src="https://github.com/user-attachments/assets/15f33db1-38ac-4412-bcc4-f2277e5f6fba" />


Data is often stored in its native format and is not cleansed, transformed or integrated, making it easier to store and access large datasets in a data lake. 

📌 A data warehouse can be created out of a data lake. 

A lakehouse is a new, open architecture that combines the best elements of data lakes and data warehouses. The [Databricks](https://www.databricks.com/product/azure) Lakehouse is designed to handle all data types (structured, semi-structured, unstructured) and powers diverse use cases. 

<img width="164" height="242" alt="rs3" src="https://github.com/user-attachments/assets/580fb00a-61f1-4277-887d-453cc9fa0377" />

For big data processing and analytics, Azure provides Databricks and Google Cloud provides Dataproc.

<img width="531" height="227" alt="csp" src="https://github.com/user-attachments/assets/9525704d-045a-417a-8734-b4a7d7176164" />


Apache Hive is an example of data warehouse which has been around since 2010. BigQuery by Google is another example releasing around the same time around, Redshift by Amazon arrived a couple of years later to handle big data, although Amazon RDS existed since 2009. 

One can [migrate data warehouses to Google BigQuery (GBQ)](https://docs.cloud.google.com/bigquery/docs/migration/migration-overview). There are similarities and differences in the syntax of SQL used in GBQ and data warehouses like [Amazon Redshift](https://docs.cloud.google.com/bigquery/docs/migration/redshift-sql), [Snowflake](https://docs.cloud.google.com/bigquery/docs/migration/snowflake-sql), [Hive](https://docs.cloud.google.com/bigquery/docs/migration/hive-sql) etc.. 

Also, cloud service providers have different storage types - object storage, file storage, etc..

<img width="858" height="56" alt="2" src="https://github.com/user-attachments/assets/4a2898b0-be18-4e12-8e8c-54a90726cb8f" />

Cloud-based Enterprise Data Warehouse (EDW) uses massive parallel processing (MPP) to quickly run complex queries across petabytes of data.

<img width="461" height="216" alt="edw" src="https://github.com/user-attachments/assets/b2831c57-cb55-483a-a8de-cfef306f70a3" />

-----

Data must be loaded into the data warehouse. The process of extracting raw data from multiple sources, transforming the data and then loading transformed data into the warehouse is called ETL (extract, transform, load). ETL is typically used to integrate structured data from multiple sources into a predefined schema.

<img width="335" height="109" alt="rs1" src="https://github.com/user-attachments/assets/7bde3210-6456-42df-9f44-36acd638a584" />


Cloud services move data between different compute and storage services, as well as on-premises data sources at specified intervals.

<img width="461" height="215" alt="etl" src="https://github.com/user-attachments/assets/cb2da134-b58c-4e1f-a2db-18b8b5cd63e0" />

# Data Orchestration

While the cloud data warehouses like Google BigQuery, Snowflake, and Databricks offer orchestration capabilities within them, they often do not provide the full range of features and flexibility offered by dedicated data orchestration tools like [Prefect](https://docs.prefect.io/v3/get-started), [Dagster](https://github.com/dagster-io/dagster), [Airflow](https://github.com/apache/airflow). 

The features of data orchestrators include dependency management, resource utilization for different stages of the data pipeline, control and alerts, data governance. The orchestration tools are important as they manage the complex workflows and execution of data pipelines that feed in and out of data warehouses. 

Dagster and Airflow have different approaches to interfacing with users which have critical implications for dependency and deployment management. Dagster enables thinking in terms of tables, files, models that data pipelines create and maintain. It has been designed to facilitate local development of pipelines, staging environment, unit testing, and code review. So, Dagster orchestrates data assets, not just tasks in a workflow. 

- [Dagster vs. Airflow](https://dagster.io/vs/dagster-vs-airflow)

[Prefect](https://github.com/haythemtellili/ml-workflow-orchestration) too is good for machine learning workflow orchestration. 

- [Dagster vs. Prefect](https://dagster.io/vs/dagster-vs-prefect)

# Data Model

**Data modeling** in a data warehouse organizes data into dimensions and facts. There are two schema kinds of data modeling - snowflake schema and star schema. It requires the tables to be classified as either dimension or fact. Dimension tables describe business entities — the things we model. Entities can include products, people, places, and concepts including time itself. Fact tables store observations or events, and can be sales orders, stock balances, exchange rates, temperatures, etc. A fact table contains dimension key that relate to dimension tables, and (numeric) measure columns. 

A **star schema** performs efficiently with large data, maintaining history and updating data by reducing the duplication of repetitive business definitions, making it fast to aggregate (query) and filter data in the warehouse. The entity-relationship diagram looks like a star hence, the schema name. 

<img width="401" height="251" alt="st" src="https://github.com/user-attachments/assets/a7308c98-1332-4496-a18a-4e8d98258749" />

Star schema is adopted in [Microsoft Power BI reports](https://learn.microsoft.com/en-us/power-bi/guidance/star-schema).
For visualization & analytics, Microsoft cloud (Azure) provides Power BI and Google Cloud provides Looker.

<img width="462" height="304" alt="av" src="https://github.com/user-attachments/assets/52d59a78-ddb7-49bc-8cda-e7e5c2a40e0e" />


The entity-relationship diagram looks like a snowflake in **snowflake schema** and it offers more storage efficiency due to its tighter adherence to less data redundancy or duplication, but slower query performance. 

<img width="401" height="209" alt="sf" src="https://github.com/user-attachments/assets/2c1d5281-b577-4572-b4f7-0d8e99e74dac" />

A snowflake schema is an extension of a star schema, where dimension tables are broken down to sub-dimensions. 

# SQL

SQL is integral to ETL or ELT. 

<img width="302" height="152" alt="rs2" src="https://github.com/user-attachments/assets/784fc21b-f106-4082-b9b7-3d5f9f7d555c" />

SQL is used for data manipulation and transformation, and for retrieving data from the data warehouse for reporting and analytical purposes. It is used for management tasks, including data archiving, indexing, performance tuning, and security management.

In RDBs, we sometimes need to combine rows from two or more tables based on a related column between them. This allows us to retrieve data spread across multiple tables and present as a single, unified result. This is where **SQL JOINS** are essential. Let's say, we have table A and table B, then following are the kinds of JOINs we can have.

<img width="515" height="160" alt="1" src="https://github.com/user-attachments/assets/abb20526-12ac-404d-8b77-eb39c2dbd2df" />

<img width="524" height="155" alt="2" src="https://github.com/user-attachments/assets/6446945e-6cec-4557-9b64-78afaa7e9818" />

<img width="515" height="191" alt="3" src="https://github.com/user-attachments/assets/28877787-bda6-4f7f-8bc5-bedef0741a50" />

Understanding how different tables relate to each other is the cornerstone of effective database querying.

---

Many potential SQL users are also [pandas](https://pandas.pydata.org/) users. A [comparison of pandas with SQL](https://pandas.pydata.org/docs/getting_started/comparison/comparison_with_sql.html) only makes us realize that operations such as LIMIT, DISTINCT, GROUP BY, WHERE, HAVING, ORDER BY, JOIN are routine work of a data professional. 

SQL and pandas serve equally well for data exploration, the latter however is more than a query engine.

<img width="214" height="38" alt="pd" src="https://github.com/user-attachments/assets/6c163851-56d9-4bc5-8712-ca9b42c963f9" />

 One can export a pandas dataframe (df) to a multitude of formats which [includes SQL](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_sql.html).

