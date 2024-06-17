# Group_1_Project_3
Group Members
--
--Zac Williams
--Joel
--Cole
--Justin
--Selena

Project Overview and Purpose
--
For our project, we focused on following the data engineering process to extract, transform, and load restaurant data. Firstly, we extracted data from websites including Yelp and Foursquare using API connections as well as sourced data from a large dataset provided by Yelp. Secondly, we transformed the data we collected by dropping null values, changed the data types of several columns and selected specific attributes to insert data into DataFrames. Third, we created an Entity Relationship Diagram with the schema from our DataFrames and used them to load the data tables into a PostgreSQL database. Lastly, we used our DataFrames to create Leaflet map and used SQLAlchemy to pull our database data into Jupyter Notebook to store it for future use.  

By utilizing APIs, Python libraries, html and a PostgreSQL database, the purpose of our project was to create a map using restaurant data along with storing said data for future use through SQLAlchemy and to display our skills in creating an ETL pipeline. Originally, our goal was to get data from 5 or more sources and compare their records; however, complications with setting up APIs had redirected our goal to its current state. 

File Organization in our GitHub Repository
--
- Project_3_Yelp_CSVs Folder: The CSV files of the data gathered from Yelp. Cleaned and structured.
- "project_3_joel_foursquare" Folder: The CSV files of the data gathered from Foursquare. Also includes our Jupyter notebook for transforming the Foursquare. 
- "selenas_data_cleaned_mapped" Folder: Contains the "Yelp Academic Dataset" CSV (selena_json.csv), our HTML code file used to create our Leaflet map (restaurants_map.html), the jupyter notebook used to tranform and clean our Yelp Academic Dataset records. 

The rest of our files outside of the project folders include our powerpoint presentation, our Entity Relationship Diagram (ERD), files used for pictures within our presenation as well as the jupyter notebook used to set up a connection between our database and the notebook (Project 3 Jupyter Notebook). Lastly, our files include the jupyter notebook we used to transform and clean our YELP API data. 

Yelp Dataset
--
In this project, the team utilized Yelp’s academic dataset. This dataset was saved in a Tape Archive Format (TAR) which allows multiple JSON datasets to be saved to an uncompressed archive file.  Due to the large size of the dataset file (9 gigabytes) we used a software utility program called 7-ZIP (7-ZIP.org) which was used to access the data. Through the 7-ZIP software program, the JSON data was saved into the following formats: SQL, CSV and Text. 


Data References
--
References for our data include Yelp (https://api.yelp.com/v3), Yelp’s open dataset (www.yelp.com/dataset), and Foursquare (https://api.foursquare.com/v3/places/search). For our API sources, we used Yelp’s fusion API and Foursquare’s Places API.

Data Sources we reviewed
--
Yelp fusion API, Trip Advisor API, Foursquare Places API, Google Places API, Door Dash, Viator, Open Table, Expedia API, Zomato API – Foreign (India and UAE Only)

Leaflet Map
--
Using the Yelp dataset and the Folium library, we were able to create a leaflet map. Folium was used to write the HTML code for our map in a jupyter notebook along with the latitudes and longitudes of locations from restaurants within our Yelp dataset. 

Challenges
--
The data was unusable in the downloaded format because each record had double brackets instead of commas to separate the libraries. We worked with the instructors to identify a way to fix the JSON data so that it could be read into Jupyter Notebook using the Visual Studio Code tools to add commas to the end of each row. Although this fixed the main file, we were unable to load the data into Jupyter Notebook due to “trailing characters” and uneven data column length. 
We decided to download the TAR/JSON data as text into Excel and used the data toolbar to convert the text into columns using the comma and colon as separators. The data conversion allowed us to access the data, however it extended the original dataset from 12 to 54 columns that needed to be reviewed and cleaned. 

The shape of the data once converted included over 150,000 businesses with 6.9 million reviews. We changed the data type to match the columns we would be using in the ERD and SQL platforms. The main columns we determined we needed to use were the business name. street address, city, state, zip code, latitude, longitude and country. There were two columns (categories and attributes) that extended across over 20 columns. Additionally, some of the data contained incorrect categories such as Home Depot being listed as a restaurant as they sell hot dogs. We used conditional formatting to identify which columns contained the category and realized that we would not be able to simply remove columns to get the data clean enough to identify the restaurants. We determined a few key words we wanted to search for and found that we needed to review each line item for “restaurants”. We then eliminated 120,000 businesses through multiple waves of sorting and deleting. While this process was inefficient, utilizing conditional formatting and removing large amounts of businesses unrelated to restaurants was the method that we used to whittle the list down to approximately 30,000 restaurants. 

We further restricted the data set to only include Florida and chose three cities resulting in a total of 865 businesses. In order to get the dataset smaller, we filtered the rating score from 3 to 5. This resulted in a data set of 317 items. We then determined that 30 columns could be removed resulting in the final columns of business name, location information, latitude, longitude, country and rating. 

Ethical Concerns/Considerations
--
Our project encountered no ethical concerns; however, we felt that we needed to disclose Yelp’s educational challenge dataset (Florida) is a static file which was archived on 1/19/2022, which contains no PII.  Yelp’s Challenge dataset is not as current as the information accessed by other team members using API calls from foursquare and Yelp. Additionally, to filter the Florida information into a smaller set of data, we removed any businesses with less than a rating of 3.
