# GoodReads Recommendation Engine

![alt text](https://github.com/akankshimody/GoodReads_Marketing_Analytics/blob/master/goodreads.PNG)

## Introduction
We are all looking for the next best book to read. As part of the Marketing Analytics Course in the MSBA Program at UT Austin, we attempted to build a recommendation engine in Python using data obtained from goodreads.

Team members: Alisha Fernandes, Akankshi Mody, Palakh Gupta, Catherine Yu Miao, Thiru Vinayagam  

## Data Used

The original data consists of two files: the first one describes books of different genres, such as children, comics, romance, non-fictions as well as another file with data describing Goodreads users, a.k.a people who provide ratings for the books. Then, we use book_id to merge the two data files together.<br><br>
Shape:  847,000+ rows x 39 cols<br>
Each row represents a rating by a goodreads user for a certain  book<br>
Variables include: Information about books, isbn, title, edition, description, format, is_ebook, authors, languages, publishers, publication dates, Information about ratings, user_id, is_read, rating score <br>

## Approach
The first step was to perform an indepth exploratory analysis. Our insights can be found in [this](https://github.com/akankshimody/GoodReads_Marketing_Analytics/blob/master/Visualizations_catherine_miao.ipynb) notebook. <br>

We then built the following models in Python:
1. [Naive model](https://github.com/akankshimody/GoodReads_Marketing_Analytics/blob/master/Item_based_filter_Thiru.py) based on KNN using cosine similarity and euclidean distance<br>
2. [Content-based filtering](https://github.com/akankshimody/GoodReads_Marketing_Analytics/blob/master/Content%20Based%20Recommendation.ipynb) using the tf-idf scores derived from the book description<br>
3. [Collaborative Filtering](https://github.com/akankshimody/GoodReads_Marketing_Analytics/blob/master/User%20Based%20Collaborative%20Filtering.ipynb)<br>
  a. Item based model using Singular Value Decomposition<br>
  b. User based model using Singular Value Decomposition

## Results
The results of our analysis and our complete presentation can be found [here](https://github.com/akankshimody/GoodReads_Marketing_Analytics/blob/master/Final%20Presentation%20-%20Group%20E.pdf).

## Conclusion
Considering the pros and cons in the all the models, and looking at our results, we recommend to customize the recommendations based on whether the user is a new user.<br>
1. New Users:<br>
We can recommend books for new users based on a Naive Model as we wouldn’t have historical information about the user's likes and dislikes to form a personalized recommendation.
2. Recurring Users: <br>
As the user-item data matrix is sparse, we would prefer using an SVD based Collaborative Filtering approach. We would implement the same on item based filtering as it provided better results than user based filtering.
