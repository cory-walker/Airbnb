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
