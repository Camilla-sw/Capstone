

**1. Collecting SpaceX launch data from the SpaceX REST API.**    

Use a get request with the requests library to obtain the launch data from SpaceX REST API endpoints, or URL:   
api.spacexdata.com/v4/launches/past.   

The response will be in the form of a JSON, specifically a list of JSON objects, each representing a launch.   

Convert this JSON to a dataframe.   

Clean the dataframe.  

Get additional information for each lauch with their ID number.  

Additional data Cleaning:  
* duplicates
* subset/filter data needed
* deal with missing values



**2. Collecting SpaceX launch data by Webscraping HTML tables**  
Use Python BeautifulSoup to web scrape HTML tables of Falcon 9 launch records. 
Then transform this raw data into a clean dataset in a Pandas data frame.

**Data Wrangling Problems:**     
* Wrangling Data using an API  
In some of the columns, like rocket, there is an identification number, not actual data.
Here I use the API again targeting another endpoint to gather specific data for each ID number.
The data will be stored in lists and will be used to create our dataset.
* Sampling Data  
Filter/sample the data to remove Falcon 1 launches and keep only Falcon9 records.
* Dealing with Nulls  
deal with the NULL values inside the PayloadMass. replace the null values in PayloadMass with the mean
