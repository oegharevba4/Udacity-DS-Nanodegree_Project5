# Udacity-DS-Nanodegree_Project5: Recommendations with IBM
 
This project analyzes the interactions that users have with articles on the IBM Watson Studio platform, and makes recommendation on unseen articles that it thinks the user will like. Three types of recommendation systems were utilised here:
 - Rank Based Recommendation
 - User Based Collaborative Filtering
 - Matrix Factorization


## Getting Started

The entire project runs on a Jupyter notebook and has the test incorporated.


## Prerequisites

The following packages needs to be installed:
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Pickle
- Python 3
- Jupyter notebook


## Files in the repository

- data<br>
    | - articles_community.csv : csv of all articles in the community<br>
    | - user-item-interactions.csv : csv of user-article interractions
    
- Recommendations_with_IBM.html : html version of jupyter notebook

- Recommendations_with_IBM.ipynb : jupyter notebook containing all the codes

- Project_tests.py : inbuilt tests imported in the jupyter notebook to test output

- top_10.p : pickle file used for testing

- top_20.p : pickle file used for testing

- top_5.p : pickle file used for testing

- user_item_matrix.p : pickle file used for testing

- README.md


## Project Summary

My project has 4 sub-headings.

#### Exploratory Data Analysis:
I visualized the data, removed duplicate rows and did some basic exploration of the dataset in a bid to understand the data and the user / article interactions.

#### Rank Based Recommendations:
All articles were ranked based on the number of interactions with users and recommendations are made uniformly to all users based on the top user / article interactions. There is no personal touch here. This is the best approach to use for a new user because we have no previous data to work with

#### User-User Based Recommendations:
Here, the relationships between users were explored to recommend documents. We found similar users where similarity is based on the intersection of articles seen by users. The higher the number of the intersection of articles seen, say by user_1 and user_2, the more similar they are.

Therefore, we can safely recommend unseen articles to user_1 from the list of seen articles by user_2, if user_1 and user_2 have been determined to be very similar.

Two methods were explored here:
- In the first method, ties in similarity and number of recommendations required were arbitrarily broken
- In the second method, users were also ranked by total number of interactions, as were articles. In the case of a tie, this rankings was used to break the tie

#### Matrix Factorization:
Here, matrices were built off the dataframe and SVD was used to make recommendations. We made use of numpy's built in SVD package because out matrix has no "NA". All "NA"s were replaced with "0"<br>
Sum of error was used to determine accuracy and we ran into an overfitting problem where the model performed well on the train set, but not as good on the test set<br>
There was also a problem of not enough common dataset between the train set and test set, (the cold start problem) therfore limiting the number of users we could predict for


## Authors

Udacity - Code template and tests<br>
Laura Egharevba - Everything else


## Acknowledgements

IBM for supplying the dataset
