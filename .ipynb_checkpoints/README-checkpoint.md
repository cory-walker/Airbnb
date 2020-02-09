## Airbnb Boston & Seattle data investigation

<b>1. Installation:</b>
All python files were created using version 3
    
<i>airbnb_wrangle.ipynb</i><br>
Imports: pandas, numpy, matplotlib.pyplot
        
<i>airbnb_data_investigation</i><br>
Imports: pandas, numpy, matplotlib.pyplot, seaborn, calendar<br>
from sklearn.linear_model import LinearRegression<br>
from sklearn.model_selection import train_test_split<br>
from sklearn.metrics import r2_score, mean_squared_error
            
<b>2. Project motivation:</b><br>
Primarily used as a case study for the Udacity Data Scientist nanodegree program, I chose this dataset due to my complete unfamiliarity with it. I have never worked with Airbnb data before, and so I was curious about whether it shared similarities to conventional hospitality data, or broke conventions
    
<b>3. Files:</b><br>
* boston_calendar.csv: Boston based rental availability data
* seattle_calendar.csv: Seattle based rental availability data
* airbnb_calendar.csv: merged Boston and Seattle calendar datasets
* boston_listings.csv: Boston based rental listing dimensions and attributes
* seattle_listings.csv: Seattle based rental listing dimensions and attributes
* airbnb_listings.csv: merged Boston and Seattle listings datasets
* boston_reviews.csv: Boston based rental user reviews
* seattle_reviews.csv: Seattle based rental user reviews
* airbnb_reviews.csv: merged Boston and Seattle user reviews datasets 
* README.md: The file you are reading right now   
* airbnb_wrangle.ipynb: Initial data wrangling, cleaning, and file merged file generation
* airbnb_data_investigation.ipynb: Data investigation of merged datasets, including graphs, tables, and observations
        
<b>4. How to interact with this project:</b><br>
1. If you are going to recreate my process from start to finish, you will first want to run the code in airbnb_wrangle.ipynb to generate the merged datasets
2. Then you can step through the airbnb_data_investigation.ipynb code
    
Starting with the following 3 questions, I began my journey through these datasets. Sadly, due to time constraints, I haven't done a thing with the review data yet.
* Q1: Does Airbnb have seasonality to their occupancy?<br>
First I thought this was simple, then I realized that Airbnb allows people to rent RVs, tents, Yurts, and boats, so I narrowed my analysis to stationary housing for a more apples to apples comparison with traditional hotels. This comparison, sadly, is not contained in this project, and only in my head.<br>
What I did discover is that they do have a typical downward trend during late fall through mid spring
* Q2: What are the major influences on room pricing?<br>
I first tried reviewing only things like room type, but then doubled back for a full Linear regression, which explained a fair amount more as Cancelllation policy, property type, # of bathrooms, and room types appear to have the most influence on pricing
* Q3: Does having a cleaning fee or security deposit affect your occupancy?<br>
For this I circled back on date plotting for a bright graph. Cleaning fees and security deposits are typically correlated to lower occupnacy, but there is an increase during the winter trend where rooms requiring a security deposit are booked more.

<b>5.Licensing, Authors, Acknowledgements</b><br>
* Udacity for having this project, and the innumerable times I referred to course materials
* Airbnb for providing this data'
* Pandas documentation authors
* Stackoverflow, for helping me in almost every coding project

## CRISP-DM notes
<b>Business Understanding</b><br>
<i>"Airbnb, Inc. is an online marketplace for arranging or offering lodging, primarily homestays, or tourism experiences. The company does not own any of the real estate listings, nor does it host events; it acts as a broker, receiving commissions from each booking." - Wikipedia</i>

This is hospitality industry data concerning pricing, rental attributes, occupancy, and guest reviews. It can provide us insight into all of those fields, and may be able to show seasonality trends over time.

<b>Data Understanding</b><br>
The original dataset contains 6 csv files, 3 pertaining to Seattle, and the other to Boston
* Calendar files contain occupancy over time data
* listing files contain rental and host attribute information
* reviews files contain guest reviews and scores

<b>Prepare Data</b><br>
The airbnb_wrangle.ipynb file contains code to perform some cleaning, and merging the boston and seattle data files into "airbnb_calendar", "airbnb_listings", and airbnb_reviews" csv files<br>
airbnb_data_investigation.ipynb contains additional cleaning code alongside data modeling, and graphing code.

<b>Data Modeling</b><br>
A Linear regression was chosen for the listing attributes in order to determine their impact on pricing. Full details, and result set are contained in the airbnb_data_investigation.ipynb file

<b>Evaluate the Results</b><br>
The graphs and tables are fully shown in the airbnb_data_investigation.ipynb file, a non-technical, simplified recap can be found on my github blog: https://cory-walker.github.io/Airbnb/, and the conclusion is below.<br>
1. We took a look at occupancy rates over time, which showed a downturn in stays during the winter months
2. We analyzed what characteristics of a rental are correlated to price, and in what direction. The evidence shows that room type, property type, number of bathrooms, and possibly the cancellation policy have strong influence over pricing.
3. We studied how cleaning fees and security deposits can have a negative impact on stays, except with a suprising turn during the low season, where rentals with security deposits experience a boon