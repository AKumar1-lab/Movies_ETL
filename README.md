# Movies_ETL 

AKumar1-lab
Angela Kumar

Module 8  Working with Extract, Transform, Load (ETL)

## Purpose
Perform Extract Transform and Load(ETL) on several movie datasets to predict popular films for a streaming service.

## Overview

Learn how to use the Extract, Transform, Load (ETL) process to create data pipelines. A data pipeline moves data from a source to a destination, and the ETL process creates data pipelines that also transform the data along the way. Analysis is impossible without access to good data, so creating data pipelines is often the first step before any analysis can be performed. Therefore, understanding ETL is an essential skill for data analysis
* Create an ETL pipeline from raw data to a SQL database.
* Extract data from disparate sources using Python.
* Clean and transform data using Pandas.
* Use regular expressions to parse data and to transform text into numbers.
* Load data with PostgreSQL.

## Resources

wikipedia-data.json(Wiki); movies_metadata.csv(Kaggle); ratings.csv(MovieLens); Deliverable 1 starter code; Deliverable 2 starter code; Deliverable 3 starter code

Software: Jupyter Notebooks, Pandas,Python, Postgresql, Anaconda3

## Background
Amazing Prime loves the dataset and wants to keep it updated on a daily basis. Britta needs your help to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. You’ll need to refactor the code from this module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database

## Deliverables

**Deliverable 1: Write an ETL Function to Read Three Data Files**
1. Create a function to read in the three files and give it a name.
2. Read in the Kaggle metadata and MovieLens ratings CSV files as Pandas DataFrames.
3. Open the Wikipedia JSON file and use the json.load() function to convert the JSON data to raw data.
4. Read in the raw Wikipedia movie data as a Pandas DataFrame.
5. Use the code provided to return the three DataFrames.
6. Use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
7. Set the three variables in Step 6 equal to the function created in Step 1.
8. Set the DataFrames from the return statement equal to the file names in Step 6. In this step, you are reassigning the variables created in Step 6 to the variables in the return statement.
In Steps 9-11, check that all three files are converted to a DataFrame. See the images below for confirmation:

<img width="500" alt="Capture reformat wiki table" src="https://user-images.githubusercontent.com/85860367/129469788-94675af5-b49a-46ae-9150-634cee94beb7.PNG">

<img width="500" alt="Capture reformat kaggle file" src="https://user-images.githubusercontent.com/85860367/129469968-e4eaa517-904e-4a94-82ca-57bab9951dab.PNG">

<img width="278" alt="Capture reformat ratings file" src="https://user-images.githubusercontent.com/85860367/129469994-585edf2d-49bd-429b-aa45-31e7194eddb3.PNG">



**Deliverable 2: Extract and Transform the Wikipedia Data**
1. Add the code from this module for the clean movie function that takes in the argument "movie".
2. Add the function you created in Deliverable 1 that reads in the three data files.
3. Inside the function you created in Deliverable 1, remove the code that creates the wiki_movies_df DataFrame from the wiki_movies_raw file, then write a list comprehension that filters out TV shows from the wiki_movies_raw file.
4. Write a list comprehension to iterate through the cleaned wiki movies list that you created in Step 3.
5. Read in the cleaned movies list from Step 4 as a DataFrame.
6. Write a try-except block that will catch errors while extracting the IMDb IDs with a regular expression string and dropping any imdb_id duplicates. If there is an error, capture and print the exception.
7. Write a list comprehension to keep the columns that have non-null values from the DataFrame created in Step 5, then create a wiki_movies_df DataFrame from the list.
8. Create a variable that will hold all the non-null values from the "Box office" column.
9. Convert the box office data created in Step 8 to string values using the lambda and join functions.
10. Write a regular expression to match the six elements of form_one of the box office data.
11. Write a regular expression to match the three elements of form_two of the box office data.
12. Add the parse_dollars() function.
13. Add the code that cleans the box office column in the wiki_movies_df DataFrame using the form_one and form_two lists created in Steps 10 and 11, respectively.
14. Add code that cleans the budget column in the wiki_movies_df DataFrame.
15. Add code that cleans the release date column in the wiki_movies_df DataFrame.
16. Add code that cleans the running time column in the wiki_movies_df DataFrame.
17. Use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
18. Set the three variables in Step 17 equal to the function created in Deliverable 1.
19. Set the wiki_movies_df equal to the wiki_file variable.
20. Check that your wiki_movies_df DataFrame looks like this image:

**Deliverable 3: Extract and Transform the Kaggle data**
The extraction and transformation of the Kaggle metadata using the ETL function does the following:
1. The Kaggle metadata is cleaned. 
2. The Wikipedia and Kaggle DataFrames are merged. 
3. The following is performed on the merged Wikipedia and Kaggle DataFrames to create the movies_df: 
    * Unnecessary columns are dropped.
    * Function is used to fill in the missing Kaggle data.
4. The movies_df DataFrame is filtered to keep specific columns.
5. The movies_df DataFrame columns are renamed.
6. The extraction and transformation of the MovieLens ratings data using the ETL function does the following:
7. The ratings counts are cleaned. 
8. The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame. 
9. The empty values in the movies_with_ratings_df DataFrame are filled with “0”. 
10. The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file. 

**Deliverable 4: Create the Movie Database**
Use your knowledge of Python, Pandas, the ETL process, code refactoring, and PostgreSQL to add the movies_df DataFrame and MovieLens rating CSV data to a SQL database.

## Summary
The exercise was difficult at times, especially transforming this to a clean dataset or reformating the code.  Extracing and Loading was easier done,however the ratings file took a long time to load as it was a larger file with 26,024,289 entries.  The Merged Movie file between Wikipedia and Kaggle, included 6,052 movies.  However considering much of it was automated, ETL tasks far outweighed traditional Excel and VBA methods.  Of course for an untrained professional there are many nuances that still need to be learned in ETL, it will take more than a week to understand ETL or work with people that have experienced this daily.
