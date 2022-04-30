## Overview
Project 1 ot the Data Engineering Nanodegree Program

Company: Sparkify
Business Goal: To understand what songs their customers are listening to using their streaming app.

Aim: To have a Data Engineer design and populate a Postgres database with tables designed to optimize queries on song play analysis.

Data: The datasets given are the Songs and Log datasets in JSON formats.

## Database Design
The **STAR SCHEMA** was chosen as a way too represent the data in tables with one FACT table (SONGPLAYS) and four DIMENSIONS tables (USERS, SONGS, ARTISTS, TIME) referencing the FACT table. This is because:
 - Queries are simplified.
 - Aggregations done on these tables are very fast
 - Saves the stress of denormalization

## ETL PROCESS
The steps in the ETL process include
1. Create FACT table from the dimension tables and log_data called songplays
2. Create DIMENSION tables (songs and artist) from extracting songs_data using selected columns.
3. Create the other DIMENSION tables (users and time) from extracting log_data using selected columns.

## FILES STRUCTURE AND USAGE
1. The SQL queries to drop, create tables and insert in them were written in the sql_queries.py file
2. create_tables.py is then run to drop and create the tables using the queries in the aforementioned file
3. etl.ipynb processes one file from song_data and log_data and loads it into tables. It contains detailed instructions on the ETL process for each tables.
4. etl.py is based on etl.ipynb and processes files from the song_data and log_data and loads them into tables.
5. test.ipynb is used to check if tables were successfully created and data was successfully loaded into them.

## ORDER OF EXECUTION OF FILES
- python create_tables.py
- python etl.py
- execute test.ipynb cell by cell
