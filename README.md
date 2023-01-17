# Foursquare Venue Scraper 2023
![alt text](images/searching.gif)

## What is it? 
**Four_Square_Venue_Search.ipynb** is a Jupyter notebook (coded in python) that exhaustively searches a custom geographic area for all venues (e.g. bars, restaurants, businesses etc.) in the area according to the Foursquare Business Directory. 

It uses the **Place Search** Foursquare API to find all venues in the area and uses the **Get Place Details** Foursquare API to get extended data on each venue (e.g. popularity, footfall, rating, price etc.). 

## What’s special about it?
-  **Exhaustive Search** - other approaches typically fail to find all venues in high density areas because the API only returns a maximum of 50 results. We use a dynamically changing search radius (i.e. smaller search radius for higher density areas) to ensure all venues are found. 
- **Custom search area** - use latitude and longitude coordinates to define any desired area to search.  
- **Effectively Free** - A search for all bars and restaurants in London cost about ~$100. Foursquare developer accounts get $200 free credit a month. 
- **Balanced speed against number of API calls** - we made the search as fast as possible whilst making as few API calls as possible.   
- **Custom Venue Types** - Easily customise the type of venues to find e.g. all businesses or just bars and restaurants etc. 
- **Tailor Data** - Can customise what extended venue data is collected via a small amount of code tweaking. 
- **Dynamic Tracker** - Track progress of search via a dynamically updated map of the search area (showing area still to be searched).  
![alt text](images/searching.gif)
- **Retrofit Different API** - Easy to retrofit a different API to exhaustively search an area e.g. Google Maps. 

## How does it work?
The **Four_Square_Venue_Search.ipynb** notebook contains a detailed explanation on how the venue search works and tips for using it. 

## How do I set up and perform the Search? 
Set up API Access: 
1. Create a foursquare developer account [here](https://location.foursquare.com/developer/) (free to create).
2. Create a new project (from your Foursquare Developer account).
3. Generate a new API key for your project.
4. Create a file called key.txt that contains the key you just generated. Save this file in the same folder as Four_Square_Venue_Search.ipynb

Perform Custom Search in Jupyter notebook:
1. Create virtual environment from requirements.txt file
2. Open **Four_Square_Venue_Search.ipynb** (using the virtual environment)
3. Enter your desired geographic area (defined by a maximum and minimum latitude and longitude) in the **Define Geographic Area** section of the notebook.
4. Review the **Setting Search Arguments** section of notebook to understand how to customise your search (e.g. what category of venues to search for). 
5. Enter your custom search paramaters in the **Perform Venue Search** section. 
6. Run all cells, the results will be saved to csv.

Output: 
The output file is a CSV with the following fields:
	•	id — The Foursquare ID for the venue.
	•	name — The name of the venue.
	•	categories — The list of categories of the venue.
	•	lat — Latitude
	•	long — Longitude
	•	num_checkins — Number of Foursquare Checkins
	•	num_likes — Number of Foursquare Likes
	•	price — Price Tier between 1-4 (i.e. −  $$$)
	•	rating — Rating for the venue.
	•	num_ratings — Number of ratings for the venue.
	•	url_venue — URL of the venue.
	•	url_foursquare — URL for the Foursquare venue.
