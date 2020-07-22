# ETL with Apache Cassandra and Python
An ETL pipeline made with Python for Apache Cassandra

## Project: Data Modeling with Cassandra
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team is particularly interested in understanding what songs users are listening to. Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

They'd like a data engineer to create an Apache Cassandra database which can create queries on song play data to answer the questions, and wish to bring you on the project. Your role is to create a database for this analysis. You'll be able to test your database by running queries given to you by the analytics team from Sparkify to create the results.

### Datasets
For this project, you'll be working with one dataset: `event_data`. The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset:
```
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv
```

### Project Template
The project template includes one Jupyter Notebook file, in which:
* It processes the `event_datafile_new.csv` dataset to create a denormalized dataset
* Models the data tables keeping in mind the queries you need to run
* Provides queries that is needed to model the data tables
* Loads the data into tables you create in Apache Cassandra and run your queries

## Project Steps
Below are steps for each component of this project.

### Modeling your NoSQL database or Apache Cassandra database
1. Design tables to answer the queries outlined in the project template
2. Write Apache Cassandra `CREATE KEYSPACE` and `SET KEYSPACE` statements
3. Develop your `CREATE` statement for each of the tables to address each question
4. Load the data with `INSERT` statement for each of the tables
5. Include `IF NOT EXISTS` clauses in your `CREATE` statements to create tables only if the tables do not already exist. We recommend you also include `DROP TABLE` statement for each table, this way you can run drop and create tables whenever you want to reset your database and test your ETL pipeline
6. Test by running the proper select statements with the correct `WHERE` clause

### To build the ETL Pipeline
1. Implement the logic in section Part I of the notebook template to iterate through each event file in `event_data` to process and create a new CSV file in Python
2. Make necessary edits to Part II of the notebook template to include Apache Cassandra `CREATE` and `INSERT` statements to load processed records into relevant tables in your data model
3. Test by running `SELECT` statements after running the queries on your database

## Table schema description
The following section describes the table schema in this project

1. music_app_history1
    * sessionId int (Primary key)
    * itemInSession int (Primary key)
    * artist text 
    * song text 
    * length float
    
2. music_app_history2
    * userId int (Primary key)
    * sessionId int (Primary key)
    * itemInSession int (Cluster key)
    * artist text 
    * song text 
    * firstName text 
    * lastName text
    
3. music_app_history3
    * song text (Primary key)
    * userId int (Primary key)
    * firstName text
    * lastName text


