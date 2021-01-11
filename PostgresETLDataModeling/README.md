### Project Description

In this project, we implemented data modeling with postgres then developed an ETL pipeline to load JSON logs generated from a streaming music service. The pipeline will help analytics team to analyze and understand what songs users are listening to.

### DataSet

Two datasets are provided:
1. Song Dataset: each file in this dataset is in Json format and contains metadata about a song and the artist of that song
2. Log DataSet: consists of log files generated based ob songs in the song dataset

### Fact and Dimension Tables
We extract relevant information from these logs and construct a Sparkify database: sparkifydb. It consists of the following tables:

- songs: contains facts about the songs in the Sparkify streaming service
- artists: contains facts about the artists whose songs are available
- users: contains facts about users who use the Sparkify service
- time: contains user activity timestamps and related time-derived columns
- songplays:  contains rows that corresponds to user' s listening activity

### ETL Pipeline
 ETL pipeline transfers data from files in two local directories(datasets) into the tables in Postgres using Python and SQ.
Below are python functions used to create required tables, insert data and write the ETL :

- create_table.py: used to establish connection to DB, create and/or drop tables if they exist
- sql_queries.py: contains all the SQL script to run ETL
- etl.py:  ETL script which connect to DB, reads dataset file, retrieve needed records  and inserts them  into the Postgres DB

### How to run the ETL
1. In the console: restart kernel then run create_table.py script to drop and create tables using command: !python create_tables.py
2. In the same console run the ETL process using this command: !python etl.py