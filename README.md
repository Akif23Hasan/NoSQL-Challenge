# NoSQL-Challenge - Module 12
This project aims to analyze the food hygiene ratings data provided by the UK Food Standards Agency. The goal is to assist the editors of the food magazine "Eat Safe, Love" in identifying establishments for future articles. 

## Requirements
* Python v3.10.9
* PyMongo
* Install Pandas
* Pretty Print (pprint)
* Import json file "establishments.json" within the "Resources" folder

## Part 1: Database and Jupyter Notebook Set Up
1)Data Import: The establishments.json file was imported into the MongoDB database using the Terminal. The database was named "uk_food," and the collection was named "establishments." The import command used is as follows:

*mongoimport --db uk_food --collection establishments --file establishments.json

2)Make sure to replace "establishments.json" with the appropriate file path if it is stored in a different location.

3)The following checks were performed to ensure the proper setup:
* Listed the databases to verify the presence of "uk_food."
* Listed the collections in the "uk_food" database to ensure "establishments" was present.
* Fetched and displayed one document from the "establishments" collection using find_one and pprint.
* Assigned the "establishments" collection to a variable for further use.

## Part 2: Update the Database
1) Add a new resturant called "Penang Flavours" to the Establishments database
2) Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields
3) Update the new restaurant with the BusinessTypeID you found.
4) Removal of Establishments in Dover: The number of documents containing the Dover Local Authority was checked, and any establishments within the Dover Local Authority were removed from the database. The number of documents was verified to ensure successful deletion.
5) Conversion of Number Values: Some number values were stored as strings instead of numbers. Using update_many, the latitude and longitude values were converted to decimal numbers, and the RatingValue was converted to integer numbers.

## Part 3: Exploratory Analysis
1) Establishments with Hygiene Score 20:
* Used count_documents to determine the number of establishments with a hygiene score of 20.
* Displayed the first document in the results using pprint.
* Converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.

2) Establishments in London with RatingValue >= 4:
* Used count_documents to find the number of establishments in London with a RatingValue greater than or equal to 4.
* Displayed the first document in the results using pprint.
* Converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.

3) Top 5 Establishments with RatingValue '5':
* Sorted the establishments with a RatingValue of '5' by the lowest hygiene score and proximity to the newly added restaurant, "Penang Flavours."
* Displayed the first document in the results using pprint.
* Converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.

4) Number of Establishments with Hygiene Score 0 by Local Authority:
* Counted the establishments in each Local Authority area with a hygiene score of 0.
* Sorted the results from highest to lowest.
* Printed the top ten Local Authority areas with the highest number of establishments with a hygiene score of 0.


## References
UK Food Standards AgencyLinks to an external site. (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GBLinks to an external site.. Contains public sector information licensed under the Open Government Licence v3.0Links to an external site.
Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).
