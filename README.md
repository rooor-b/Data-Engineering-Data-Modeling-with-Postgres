# Project Description (Data Modeling with Postgres)

In this project I used python to:
    - Create star schema database ***sparkifydb*** on postgres, optimized for queries on song play analysis 
    - Create  ETL pipeline in Postgres to extract, transfer and load data from songs dataset into **sparkifydb** schema.
the output after running the project are:
## Fact Table
### songplays:  
> contains records in log data associated with song plays i.e. records with page NextSong:  
* songplay_id
* start_time
* user_id
* level
* song_id
* artist_id
* session_id
* location  

## Dimension Tables
### user_agent:
> Contains record of users in the app:
* user_id
* first_name
* last_name
* gender
* level
### songs: 
> Contains records of songs in music database:
* song_id
* title
* artist_id
* year
* duration
### artists:
> Contains records of artists in music database:
* artist_id
* name
* location
* latitude
* longitude

 ###  time:
> Contains timestamps of records in songplays broken down into specific units:
* start_time
* hour
* day
* week
* month
* year
* weekday

# Files
* **test.ipynb** displays the first few rows of each table to let you check your database.
* ***create_tables.py*** drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
* ***etl.ipynb*** reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.
* ***etl.py*** reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
* ***sql_queries.py*** contains all your sql queries, and is imported into the last three files above.
* ***README.md*** contains description of project
* ***erd.jpg*** show entity relational diagram

### Run Project

To create ***sparkifydb*** schema and create fact and dimention tables run 

```sh
$ python create_tables.py
```
Note: you have to run  create_tables.py each time you want to drop tables and create them again.

To create the ***ETL*** pipeline run  
```sh
$ python etl.py
```
run test.ipynb to make sure that data is loaded successfully into **sparkifydb** tables.