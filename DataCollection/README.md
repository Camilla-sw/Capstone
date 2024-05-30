

**1. Collecting SpaceX launch data from the SpaceX REST API.**  
The SpaceX REST API endpoints, or URL:   
api.spacexdata.com/v4/launches/past.   

To get the data from the API, perform a get request with the requests library to obtain the launch data. 
This result can be viewed by calling the .json() method. 
Since we are using an API, the response will be in the form of a JSON, specifically a list of JSON objects, each representing a launch.   

To convert this JSON to a dataframe, we can use the json_normalize function. 
This function will “normalize” the structured json data into a flat table.   
data = pd.json_normalize(response.json())



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
