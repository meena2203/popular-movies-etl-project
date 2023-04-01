# Team_3_project_2
Team 3 Technical Report
Meena Rai, Ryan Marshall, Joshua Samuel

# Objective
The objective for this project is to find the most popular movies and tv shows across different streaming services.

## Data Sources
https://www.kaggle.com/datasets/victorsoeiro/netflix-tv-shows-and-movies

https://www.kaggle.com/datasets/victorsoeiro/disney-tv-shows-and-movies?select=titles.csv

https://developers.themoviedb.org/3/getting-started/introduction

# Methodology
## EXTRACT
For this project, we worked with multiple movie datasets to try to find the most popular movies and tv shows from different streaming platforms such as Netflix and Disney+, and put them into one database. 

* The first step for this project was to extract the data from a variety of sources. The Netflix and Disney+ datasets were csv files taken from Kaggle with over 7000 lines of data. After downloading the datasets, we loaded them into Pandas dataframes using Python. 
* We then extracted data from The Movie Database(TMDB) using an API request to get a wider range of the most popular movies and tv shows in a JSON format. To put the TMDB data into a dataframe, we had to iterate through the list using a for loop and add the data to a Pandas dataframe as shown below:

## TRANSFORM
### Transformation of Disney+ and Netflix DataFrames
After we had extracted all the data from the Netflix and Disney+ csv files and put them into dataframes, we then had to transform the data to fit our needs. Below are the list of transformations we performed:
* Create new dataframe with desired columns
* Combined the Disney+ and Netflix DataFrames into one dataframe
* Below shows the before and after of the dataframes:
	Before:
	After:

### Transformation of TMDB DataFrames
We also had to transform the TMDB dataframe to match our needs. Below are the transformations performed on the data:
* Renaming of the TMDB Movie DataFrame columns to match the Disney and Netflix DataFrame
* Renaming of the TMDB TV DataFrame columns to match the Disney and Netflix DataFrame
* Made new clean TMDB movie and tv DataFrames containing only the columns we need
* Added a type column to the cleaned movie database with type as “MOVIE”
* Added a type column to the cleaned show database with type as “SHOW”
* Combined the cleaned movie and tv Dataframes into one Dataframe and reset the index
* Found any null values in the ‘release_year’ column and dropped them
* Formatted the ‘release_year’ column to match the Disney/Netflix DataFrame format (only year)

### Transformation of Final DataFrame
We also transformed the final dataframe to match our needs. Below are the transformations performed on the final dataframe:
* Combined the Movie/TV Dataframe with the Netflix/Disney Dataframe
* Dropped rows with NaN value for ‘tmdb_popularity’ column
* Dropped rows with duplicate titles
* Sorted DataFrame in descending order by TMDB popularity and reset the index

# LOAD
## Creating the Schema
After extracting and transforming the data to match our needs, we then had to load the data into a database. We chose to use a Relational SQL structure using postgres to store the data. Below is the schema for our database: 

## Loading the data to the database
To do this, we used SQLAlchemy to connect Python to PGAdmin and loaded our data using the to_sql function. 

