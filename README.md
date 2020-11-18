# 1. Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goal.

## Repository
The reposity loads JSON log data and song metadate to a Postgres database. 
The data files used...
* log_data
* song_data

## Database Creation
The purpose of this project is to create a database that the analytics team at Sparkify can used to analyze
data collected about songs and user activity on their streaminmg app. Before the creation of this database
system the company did not have an easy way to query data.


# 2. State and justify your database schema design and ETL pipeline.

## Database Schema Design
The database is broken down into 5 different tables (song_plays, users, songs, artist, time) in order 
to organize the data so that the analytics team at Sparkify can get insites on these different topics.
The song_plays table is the fact table. The users, songs, artist and time tables are dimension tables. 
In the star schema this would mean that song_plays is the table that the others branch out from.

## ETL Pipeline
Extract --> Transform --> Load
* Data is extracted from data file which contains song and log data in JSON format
* Data in JSON format is transformed into dataframes 
* Dataframes are created are loaded into the tables that were created in the Postgres database
* log_data requires more transformation than song data to create tables
* song_data ==> songs, artist tables
* log_data ==> users, song_plays, time tables

## Files
 * create_tables.py
     * creates the database
     * drops tables if they already exist
     * create tables
 * etl.ipynb
     * acts as scractch paper for testing out of coding to the ETL pipeline
 * etl.py
     * processes data from log and song files
     * inserts the processed data into the database and tables
 * sql_queries.py
    * stores all sql queries, including those which are used to create tables
 * test.ipynb
    * used the test it the etl is correctly transforming and inserting data into tables

