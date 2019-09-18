### Predict Listing Price for AirBnB Seattle 
The Project is part of Udacity Data Scientist Nanodegree


### Overview:
The project used a Kaggle Dataset containing data for Seattle Airbnb listings during 2016.
The project followed the CRISP-DM method of data exploration as follows:
1.	Business Understanding
2.	Data Understanding
3.	Data Preparation
4.	Modeling
5.	Evaluation
The objective of the project is to predict listings price along with the important features driving the listing’s Price on AirBnB.
 

### Data:
Listings.csv: Provides comprehensive details about each listing including host details, location description and details, and review ratings etc.
The above data is exhaustive given the objective of the project and is used to answer the questions which were well laid before starting the project.


### Installations:
We used Anaconda environment with Python 3.6

### Motivation:
We need to come up with some questions related to the data and answer them through data analysis.
Following are the questions as per the Business Understanding.
Question 1: How to predict price of the new listing?
Question 2: Which ML technique will be most suitable for the price detection based on the available data?
Question 3: What are the most important features driving the listing price? 


### Data Understanding and Preparation:
#### Data Wrangling 
An extensive review of the available attributes in the data was conducted. Fields that did not fit within the proposed business case in any way were dropped for e.g. IDs & URLs etc. Some features with high missing values (greater than 20%) were dropped readily. Missing rows for attributes like beds, bedrooms, bathrooms were replaced with zeros. Type conversions were performed as necessary. 

#### Feature Engineering
Important features like property type and accommodation type though categorical in nature explains the listing features very well, so they were recoded as necessary into dummy variables.

Neighborhood of a listing which could be an important feature determining the listing price is recoded into dummy variables.

Amenities attribute had 42 unique amenities out of which similar amenities were clubbed together and were finally recoded into dummy variables. In order to make sure that there is no correlation problem in newly created amenities dummies, a correlation test was conducted as below which confirmed very less correlation among these variables.

![Equalizer](https://github.com/ketanchangotra/Udacity-Project/blob/master/Correlation%20chart.png)

#### Feature Inclusion
After dropping, recoding and engineering new features as discussed above, we have total 80 variables including listing’s Price which will go into model development stage for Price prediction.
Before model development we need to understand dependent variable trend which has right skewed distribution with median=100 and mean=127.

![Equalizer](https://github.com/ketanchangotra/Udacity-Project/blob/master/Price%20Distn.png)

### Model Development & Key Findings:
Since there are a few listing attributes with missing values, the model predicting Price is developed using XGBOOST ML technique which has inbuilt functionality to take care of missing values. 

The Fine-tuned Model performed with Mean Absolute Error of 26 on Training sample and 23 on Test Sample.

We ranked all the listing attributes used to predict Price as per the feature importance and ranked them as follows.

![Equalizer](https://github.com/ketanchangotra/Udacity-Project/blob/master/Feature%20Importance.png)

Following is the list of top fifteen attributes explaining the Price.
- Reviews per Month
- No.of Accomodates
- Availability in 365 days
- No. of Bathrooms
- Reviews score rating
- No. of Bedrooms
- No. of Host Listings
- No. of Guests
- Minimum Nights Stay
- No. of Reviews
- Capitol Hill as the Neighborhood
- Availability in 30 days
- Downtown as the Neighborhood
- No. of Beds
- Availability in 90 days

### Licensing, Authors, Acknowledgements, etc.
The project has been completed by myself.





