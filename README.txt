RECOMMENDATION SYSTEM FOR MOVIELENS
An Exploratory Data Analysis Performed by Nnamdi Leonard

-------------------------------------------------------------------------------------------------------------------
Order Of Execution:
- Understanding the Business Requirement/Goal
- Understanding the Data
- Importation of required Python dataset
- Pre-Processing
- Content-Based Recommender Algorithm
- Recommendation

-------------------------------------------------------------------------------------------------------------------
BUSINESS UNDERSTANDING 

This is about a user we'll call Sam for the sake of this analysis. Sam is a subscriber of the company's online 
streaming service, and I have been tasked to give recommendations for movies he might like based on the his 
streaming history and rating. The Recommendation System used is built around the ideology of the Market Basket
Analysis of Unsupervised Learning Techniques in Machine Learning.


UNDERSTANDING THE DATA 

This dataset describes 5-star rating and free-text tagging activity from MovieLens, a movie recommendation service.
It contains 22884377 ratings and 586994 tag applications across 34208 movies. These data were created by 247753 
users between January 09, 1995 and January 29, 2016. This dataset was generated on January 29, 2016. Users were 
selected at random for inclusion. All selected users had rated at least 1 movies. No demographic information is 
included. Each user is represented by an id, and no other information is provided.

The dataset was downloaded from IBM cloud object storage. The data are contained in four files, links.csv, 
movies.csv, ratings.csv and tags.csv but the focus will be strictly on two files; 'movies.csv' and 'ratings.csv':


Ratings Data File Structure (ratings.csv)
-----------------------------------------

All ratings are contained in the file `ratings.csv`. Each line of this file after the header row represents one 
rating of one movie by one user, and has the following format: userId,movieId,rating,timestamp

The lines within this file are ordered first by userId, then, within user, by movieId.

Ratings are made on a 5-star scale, with half-star increments (0.5 stars - 5.0 stars).

Timestamps represent seconds since midnight Coordinated Universal Time (UTC) of January 1, 1970.


Movies Data File Structure (movies.csv)
---------------------------------------

Movie information is contained in the file `movies.csv`. Each line of this file after the header row represents one 
movie, and has the following format: movieId,title,genres

Movie titles are entered manually or imported from <https://www.themoviedb.org/>, and include the year of release 
in parentheses. Errors and inconsistencies may exist in these titles.

Genres are a pipe-separated list, and are selected from the following:

* Action
* Adventure
* Animation
* Children's
* Comedy
* Crime
* Documentary
* Drama
* Fantasy
* Film-Noir
* Horror
* Musical
* Mystery
* Romance
* Sci-Fi
* Thriller
* War
* Western
* (no genres listed)

-------------------------------------------------------------------------------------------------------------------
PRE-PROCESSING

This includes the following processes:

- Importation of the required libraries

- Reading the csv files to it's DataFrame format.

- Extracting the year tag from the movies and creating a new column for the extracted year.

- Created a copy of the movie dataset in order to convert the genre list into a vector format using the One Hot
  Encoding Technique.


-------------------------------------------------------------------------------------------------------------------
CONTENT-BASED RECOMMENDER ALGORITHM:

- Defining the user input in order to perform learning processes.

- Using the Dot function to create weighted values for the input.

- Commence recommendation by extracting the genre table from the duplicate dataset itself

- Then calculate the weighted average which is calculated thus: (genreTable*genreWeight).sum(axis=1))/(genreWeight.sum()

- Using '.loc' we are able to provide the recommended table from the dataset


THANKS FOR YOUR TIME