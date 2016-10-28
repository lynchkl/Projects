#Predicting Michelin Star Restaurants in DC
##Overview
To predict DC Michelin stars, I began by scraping data on thousands of restaurants in NYC, SF and Chicago (the 3 other US cities with Michelin stars) and DC. I chose this data because most Michelin star restaurants are Zagat-reviewed. 
<p align ="center">
<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/Zagat.png" />
</p>

I began with exploratory data analysis: 
<p align ="center">
<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/food%20ratings.png" />

<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/food%20ratings2.png" />

<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/cuisines.png" />

<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/price.png" />
</p>

Based on the characteristics of my data and EDA, I used a random forest regression model: 
<p align ="center">
<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/model.png" />

<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/model2.png" />
</p>

To my chagrin, price was the strongest predictor in this model:
<p align ="center">
<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/importances.png" />
</p>

My model predicted 4 of the 12 Michelin star restaurants. Fatally, 5 of the winning restaurants weren't included in my dataset because they didn't have Zagat reviews (Inn at Little Washington was excluded based on geography). Michelin restaurants may be Zagat-reviewed elsewhere in the country *because* they are Michelin restaurants. 

<p align ="center">
<img src ="/Predicting%20DC%20Michelin%20Restaurants/images/results.png" />
</p>

##Files included in this repository: 

###[Research & Zagat scraping](/Predicting%20DC%20Michelin%20Restaurants/files/Research%20&%20Zagat%20scraping.ipynb)
This document includes research notes and the syntax to scrape ratings data from Zagat.

###[Cleaning Zagat data](/Predicting%20DC%20Michelin%20Restaurants/files/Cleaning%20Zagat%20data.ipynb)
This syntax aggregates datasets and drops duplicates and unnecessary variables.

###[Scraping Michelin](/Predicting%20DC%20Michelin%20Restaurants/files/Scraping%20Michelin%20.ipynb)
In this code I use Beautiful Soup to scrape Michelin restaurant names/stars from the Michelin website.

###[Zagat-Michelin merge](/Predicting%20DC%20Michelin%20Restaurants/files/zagat-michelin%20merge.ipynb)
Syntax to merge Zagat and Michelin data on restaurant name. Includes checking control totals and mismatches.

###[Michelin EDA](/Predicting%20DC%20Michelin%20Restaurants/files/Michelin%20EDA.ipynb)
Exploratory data analysis, which includes looking at relationships between: 
* Michelin stars and Zagat cuisine type
* Michelin stars and being on Open Table
* Price distribution between Michelin and non-Michelin restaurants
* Michelin stars and Zagat food, service and decor ratings
* Zagat food ratings across cities
* Zagat food costs across cities

###[Michelin models](/Predicting%20DC%20Michelin%20Restaurants/files/Michelin%20models.ipynb)
Modeling, including the final model and submission output. Techniques used include:
* Feature engineering: imputing missing values, label enconder for cuisine type, normalizing price by city
* Train-test-split, training on NYC & SF, testing on Chicago
* Due to the nature of the data (ordinal, dummy & continuous) models focus on CART options; final model is random forest regression
* Assessed using confusion matrices and feature importances

###[Presentation](/Predicting%20DC%20Michelin%20Restaurants/files/Presentation.pptx)
PowerPoint presentation
