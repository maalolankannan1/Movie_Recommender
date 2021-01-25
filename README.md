# Movie Recommendation System
A Movie recommendation system using KNN <br><br>
## FLOWCHART
<image src = "./OUTPUTS/FLOW2.jpg"></image>
<br>
## DATASET USED
The data set used for this project is the 1M ratings data set from <a href= "https://grouplens.org/datasets/movielens/"><b>MovieLens</b></a>. This contains 1 Million ratings of movies from 7120 movies and 14,025 Users. This data set includes -
-	MovieId
-	Title
-	UserId
-	Ratings
-	Genres

That are spread into 2 files - ‘movies.csv’ And ‘ratings.csv’.
The ‘movies.csv’ file contains MovieId, Title and Genres as columns and the ‘ratings.csv’ file contains UserId, MovieId, Ratings and Timestamp as columns.

## INTRODUCTION
A recommendation system is a subclass of information filtering system that seeks to predict the "rating" or "preference" a user would give to an item. They are primarily used in commercial applications. 
A wide range of applications of recommendation systems are provided to the user. The popularity of these recommendations systems have gradually increased and are recently 
implemented in almost all online platforms that people use to give them a more personalized experience. The content of systems differs from films, podcasts, books and videos, to 
commodities on e-commerce websites, to people on commercial and dating websites. These recommendation systems are very important to attract the users. 

## ANALYSIS
In the MovieLens dataset there will be many movies for which very few users would have reviewed. Without considering the number of ratings per movie, our analysis will not lead 
to correct results. Therefore before predicting, all the movies with less than 30 reviews are excluded. Then they are sorted only based on their Average rating. For displaying 
Top movies of any genres this would be helpful. After merging the UserId and knowing which user reviewed which movies, a function can be written to find out a movie that has been 
mostly watched by the users who have watched a particular movie. This is like ‘Users who have watched this movie have also watched…’. This is done by the get_other_movies() 
function. These kind of classifications are naïve and a better solution can be done to improve accuracy of prediction. For this the K-Nearest Neighbour classifier is used. 
For performing Knn classification, a filtered ratings table (movies having more than 10 reviews) is taken. Using a pivot() function the UserIds are taken as the rows and the 
MovieIds are taken as columns. Knn is used on this Pivoted table. As we need the top 10 nearest neighbours, the number of neighbours for Knn function is given as 11(The movie 
searched itself will be considered as the nearest neighbour). The model_knn_kneighbours() function helps us to find the nearest neighbours.

## EXAMPLES

To get other top 10 movies watched by the users who have watched the particular movie given as an input( Here "Inception(2010)")<br>
<image src = "./OUTPUTS/13.JPG"></image><br>

To get the Top 10 similar movies of the particular movie taken as input parameter( Here "Matrix(1999)") by using the KNN Classification.<br>
<image src = "./OUTPUTS/18.JPG"></image><br>
