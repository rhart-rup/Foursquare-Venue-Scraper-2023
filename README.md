# Foursquare Venue Scraper 2023
![alt text](images/searching.gif)

## What is it? 
**Four_Square_Venue_Search.ipynb** is a Jupyter notebook that exhaustively searches a custom geographic area for all venues (e.g. bars, restaurants, businesses etc.) in the area according to the Foursquare Business Directory. 

It uses the **Place Search** Foursquare API to find all venues in the area and uses the **Get Place Details** Foursquare API to get extended data on each venue (e.g. popularity, footfall, rating, price etc.). 

## What’s special about it?
-  **exhaustive search** - other approaches typically fail to find all venues in high density areas because the API only returns a maximum of 50 results. We use a dynamically changing search radius (i.e. smaller search radius for higher density areas) to ensure all venues are found. 
- Balanced search speed against the number of API calls made -> we made the search as fast as possible whilst making a small number of API calls.   
- Easily customise the type of venues to find e.g. all businesses or just bars and restaurants etc. 
- Structured such that a small amount of code tweaking can change what extended venue data is extracted. 
- Track progress of search via a dynamically updated map of the search area (showing area still to be searched).  
![alt text](images/searching.gif)
- Easy to retrofit a different API to exhaustively search an area with e.g. Google Maps. 

## How to set up 

Foursquare Account: 
- Key file + Foursquare Account
Setting Parameters in Jupyter File: 
- Define Geographic Area
- Categories List
- Tune Search Parameters (Initial Search Radius, time between updates)
- Choose whether to use multi search (gets an extra maybe 10% or fewer venues, but makes far more calls and runs for many times longer e.g. maybe 10x more)
- Run all and spit out results

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
