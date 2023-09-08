# Final-Project-Statistical-Modelling-with-Python
My research centered on the examination of businesses in proximity to different bike stations within New York City, with the aim of uncovering potential relationships between the availability of bikes at these stations and the ratings of the businesses situated nearby.

## Process
Data Retrieval: Initially, I utilized the City Bikes API to obtain information about bike stations within New York City. This yielded a total of 1979 bike stations, including their respective latitude and longitude coordinates.

Business Data Collection: Subsequently, I sent requests to both Foursquare and Yelp APIs to retrieve data on businesses situated within a 1000-meter radius of each bike station. I imposed a limit of 50 businesses per bike station in my requests.

API Selection: After evaluating the results from both APIs, I chose to utilize the data from the Yelp API, as it provided more comprehensive information aligned with my research goals. However, due to rate limits imposed by the Yelp API, I reduced the number of bike stations from 1979 to 1000. This yielded a dataset comprising 30,000 businesses.

Data Integration: To consolidate the information from the City Bikes data and the Yelp API data, I merged these datasets into a single dataset. This enabled me to have pertinent data like station names, bike counts, ratings, and the number of reviews in one coherent table.

Data Storage: For efficient management of this data, I created an SQLite3 database and stored this integrated dataset within it.

Exploratory Data Analysis (EDA): To gain insights and a better understanding of the dataset, I conducted exploratory data analysis. This process also served as a verification step to ensure that the merge was successful and that all the necessary data was present and accurate.

Data Aggregation: I then grouped the data by station name, calculating the average ratings for all the corresponding businesses while retaining information about the number of bikes available at each station. This reduction step reduced the dataset from 30,000 rows to 1000 rows, with each row representing a bike station.

Regression Model: Lastly, I developed a regression model to establish a quantitative relationship between the number of bikes at each station and the ratings of the businesses within a 1000-meter radius of that station. This model aimed to provide insights into potential correlations between these variables.

## Results
In the specific domain I focused on, the Yelp API emerged as the superior choice in terms of data quality, as it provided a more extensive dataset in two critical aspects: the quantity of data points for each business and the overall number of businesses retrieved. Specifically, the Yelp API furnished a substantial dataset of 30,000 businesses associated with 1000 bike stations, whereas the Foursquare API yielded a significantly smaller dataset, consisting of only 7,733 businesses.

Regarding the model I constructed, I successfully established a statistically significant relationship between the independent variable, which was the number of bikes available at each station, and the dependent variable, which represented the ratings of the businesses. However, it's important to note that despite the statistical significance, this relationship exhibited a degree of weakness, as indicated by the low R-squared value. This observation suggests that while there is a measurable association between the number of bikes and business ratings, there are likely other factors at play that contribute to the ratings, and the number of bikes alone may not be a robust predictor of business success.

## Challenges 
During the course of my project, I encountered several notable challenges that presented hurdles to my progress. Firstly, adapting to a new working environment proved to be a struggle, particularly when it came to importing the necessary libraries. These libraries were installed in a different environment, causing compatibility issues and hindering my workflow.

Additionally, I faced difficulties with the Yelp API. Unbeknownst to me at the outset, there was a strict daily limit of 500 requests imposed by the API. Unfortunately, I initially attributed this constraint to errors in my code, which led me to spend valuable time troubleshooting issues that were, in fact, beyond my control.

Lastly, I grappled with the complexities of constructing the regression model. The data I had collected did not readily yield data points demonstrating a strong and discernible relationship between variables. This posed a significant challenge in determining how to proceed with the modeling, as the absence of clear and significant relationships made it difficult to draw meaningful conclusions from the data.

## Future Goals
Looking ahead to the future, one area of learning that I'm particularly keen to delve into is error handling. I aspire to enhance my proficiency in effectively identifying and comprehending errors that may arise from my code. This skill will not only assist in troubleshooting and resolving issues but also contribute to the overall robustness and reliability of my programming endeavors.
