# Movies_ETL

## Background

While ETL can absolutely be used for a one-time transfer of data, it becomes really powerful when it can be automated as a repeated, ongoing process. Since this process will be running necessary to perform the exploratory data analysis steps. However, if new incoming data contains errors, the ETL process may hault or produce corrupted data. Adding try-except blocks will make the automated ETL script more robust to error. 

## Objectives 

•	Create an automated ETL pipeline 

• Extract data from multiple sources 

•	Clean and transform the data automatically using Pandas and regular expressions 

•	Load new data into PostgreSQL 

## Instructions 

1.	Create a function that takes in three arguments:

•	Wikipedia data 

•	Kaggle metadata 

•	MoviesLens rating data (from Kaggle)

2.	Use the code from your Jupyter Notebook so that the function performs all of the transformation steps. Remove any exploratory data analysis and redundant code.
3.	Add the load steps from the Jupyter Notebook to the functions. You’ll need to remove the existing data from SQL, but keep the empty tables.
4.	Check that the functions works correctly on the current Wikipedia and Kaggle data.
5.	Document any assumptions that are being made. Use try-except blocks to account for unforeseen problems that may arise with new data.

## Assumptions

1.	Add try-exempt blocks to the data to account imdb.id character count (extracting only ids with 7 characters).
2.	Assume the imported wiki file needs to be cleaned.

	rename the columns names to make them more readable

	clean the wiki data leaving only the original movie title

	transform the wiki data to a dataframe

	remove columns that are missing 90% of the data. The columns that are missing the data cannot be used for analysis

3.	Transform the column datatypes to match the data in the row

	transform the box_office column data using regular expressions

	change the box_office datatype to numeric

	transform the budget data column using regular expressions

	change the release_date to datetime datatype using regular expressions

	change the running_time to reflect the correct datatype.

	After transformation extract box_office, budget, release_date and running_time data to new columns in the DataFrame

	drop the original columns

4.	Assume the kaggle_metadata columns do not have correct datatypes

	Change the budget, id, popularity column datas to numeric values

	Change the release_date and to datetime values using pandas

5.	When merging the Wikipedia and Kaggle dataframes assume that several columns will be duplicates

	inspect the merged dataframe to remove the duplicate columns

	before dropping the duplicate columns, make sure that the columns kept have the complete data for the analysis
