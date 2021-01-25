# airbnbseattledataset
This repository consists in a jupyter notebook with exploration of the Seattle Airbnb dataset.
Motivation for this repostory consists in gaining experience working with python libraries such as numpy, pandas, matplotlib, seaborn and sklearn.
The usage of real world data is an incentive to present this project as a blog post on medium.

https://alejandrosierra-53137.medium.com/should-i-post-my-apartment-in-airbnb-6fdd7c4b4a10

Dataset can be found here
https://www.kaggle.com/airbnb/seattle/data

Business Understanding
Focus for this analysis is based on three indicators that, in my opinion, are the most important to understand business in the house rental field.
Those indicators are price, reviews and availability.
In particular, I analyze the following:
  - Neighbourhood differences in price
  - Neighbourhood differences in availabilty
  - Price by property type and bed type
  - Reviews by property type and bed type
  - can we predict price for a house?
  - can we predict reviews for a house?
  - can we predict availability for a house?

Data Understanding
- calendar: For every house, we have the information of price and availability day by day. In total, it adds up to over 1 million observations
- reviews: For each house there is a review identified with date, the reviewer and the comment made.
- listings: Gives information about several aspects of the booking. Can be divided in sections, host, house description, neighbourhood, booking conditions, reviews.

Prepare Data:

Data quality issues addressed:
- calendar df:
  - convert date to datetype
  - convert available to boolean
  - convert price to int/float

- reviews df:
  - convert date to datetype

-listings df:
  - drop license column
  - drop neighbourhood, work with neighbourhood_group_cleansed and neighborhood_cleansed columns. Use neighbourhood_cleansed_group instead
  - drop square feet. Too many nan
  - neighborhood_overview copy according to neighbourhood_cleansed
  - space, notes create dummy variable or count words
  - transit, thumbnail_url, medium_url, xl_picture_url create dummy variable 0 or 1
  - host_about create count words
  - host_acceptance_rate, host_response_rate and host_response_time fill with mode
  - host_is_superhost convert to bool
  - weekly price and monthly price to int. a lot of nans. Fill with price
  - security_deposit, cleaning_fee fill with 0
  - first and last review to dtype
  - review_scores fill with mean
  

Data Modeling and Results evaluation
First four questions can be answered with descriptive analitics.
For predictions, I used Decission Trees Classifier and Regression Model.
Trees were much better in predicting reviews and availability.
Price did not get good enough accuracy so it is better to address this question with descriptive plots ans visualizations.
