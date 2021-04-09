# Data Modeling with Postgres

## Introduction

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

## Project Description

In this project, you'll apply what you've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, you will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

## Prerequisites

This project makes the folowing assumptions:

* Python 3 is available
* `pandas` and `psycopg2` are available
* A PosgreSQL database is available on localhost

## Running the Python Scripts

At the terminal:

1. ```python create_tables.py```
2. ```python etl.py```

In IPython:

1. ```run create_tables.py```
2. ```run etl.py```


## Schema for Song Play Analysis
Using the song and log datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

### Fact Table

**songplays** - records in log data associated with song plays i.e. records with page NextSong

- songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
**users** - users in the app

- user_id, first_name, last_name, gender, level

**songs** - songs in music database

- song_id, title, artist_id, year, duration

**artists** - artists in music database

- artist_id, name, location, latitude, longitude

**time** - timestamps of records in songplays broken down into specific units

- start_time, hour, day, week, month, year, weekday

## Description of Files

- data
    
    --log_data   This directory contains a collection of JSON log files. 
    
    --song_data  This directory contains a collection of Song JSON files.
    
- create_tables.py This Python script recreates the database and tables used to storethe data.

- etl.ipynb A Python Jupyter Notebook that was used to initially explore the data and test the ETL process.

- etl.py This Python script reads in the Log and Song data files, processes and inserts data into the database.

- sql_queries.py A Python script that defines all the SQL statements used by this project.

- test.ipynb A Python Jupyter Notebook that was used to test that data was loaded properly.
