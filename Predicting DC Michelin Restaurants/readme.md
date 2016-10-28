To predict which DC restaurants would receive Michelin stars, I began by scraping data on thousands of restaurants in NYC, SF and Chicago (the three other US cities with Michelin stars) and DC. I chose this data because most Michelin star restaurants are Zagat-reviewed. 


##Files included in this repository: 

###Research & Zagat scraping
This document includes research notes and the syntax to scrape ratings data from Zagat.

###Cleaning Zagat data
This syntax aggregates datasets and drops duplicates and unnecessary variables.

###Scraping Michelin
In this code I use Beautiful Soup to scrape Michelin restaurant names/stars from the Michelin website.

###Zagat-Michelin merge
Syntax to merge Zagat and Michelin data on restaurant name. Includes checking control totals and mismatches.

###Michelin EDA
Exploratory data analysis, which includes looking at relationships between: 
* Michelin stars and Zagat cuisine type
* Michelin stars and being on Open Table
* Price distribution between Michelin and non-Michelin restaurants
* Michelin stars and Zagat food, service and decor ratings
* Zagat food ratings across cities
* Zagat food costs across cities

###Michelin models
Modeling, including the final model and submission output. Techniques used include:
* Feature engineering: imputing missing values, label enconder for cuisine type, normalizing price by city
* Train-test-split, training on NYC & SF, testing on Chicago
* Due to the nature of the data (ordinal, dummy & continuous) models focus on CART options; final model is random forest regression
* Assessed using confusion matrices and feature importances

###Presentation
PowerPoint presentation
