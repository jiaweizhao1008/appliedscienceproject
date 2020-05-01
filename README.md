AppliedScienceProject - Hotel Review Analysis
==============================
* Author: Jiawei Zhao
* Created Time: April 30, 2020

The dataset is download from Kaggle: https://www.kaggle.com/jiashenliu/515k-hotel-reviews-data-in-europe.
This dataset contains 515,000 customer reviews and scoring of 1493 luxury hotels across Europe. Meanwhile, the geographical location of hotels are also provided for further analysis.

The main goal of this project is to analyze the hotels' situation and predict the sentiment based on reviewers' comments. To apply what I learned from this course, I used the data analysis, data visualization, data preprocessing, create the logistic regression model, and evaluate the model in this project. Based on the analysis, we can see hotels' situation more clearly, like the top 20 popular hotels, hotel location, hotel rating, and so on. I also used the word cloud to display text occurrence. Apply the bag of words and TFIDF model to process the text, and finally, use the logistic regression to predict the sentiment and evaluate the model performance.

The code file is saved under the notebooks file, called HotelReviewsAnalysis.ipynb (https://github.com/jiaweizhao1008/appliedscienceproject/blob/master/notebooks/HotelReviewsAnalysis.ipynb). The html file is saved in reports/HotelReviewsAnalysis.html (https://github.com/jiaweizhao1008/appliedscienceproject/blob/master/reports/HotelReviewsAnalysis.html).

The raw data could be download by this link: https://www.kaggle.com/jiashenliu/515k-hotel-reviews-data-in-europe/download.
The data used to train model is saved in src/data/sentiment.csv.zip (https://github.com/jiaweizhao1008/appliedscienceproject/blob/master/src/data/sentiment.csv.zip). 

Data Content
-------------
The csv file contains 17 fields. The description of each field is as below:

* Hotel_Address: Address of hotel.
* Review_Date: Date when reviewer posted the corresponding review.
* Average_Score: Average Score of the hotel, calculated based on the latest comment in the last year.
* Hotel_Name: Name of Hotel
* Reviewer_Nationality: Nationality of Reviewer
* Negative_Review: Negative Review the reviewer gave to the hotel. If the reviewer does not give the negative review, then it should be: 'No Negative'
* ReviewTotalNegativeWordCounts: Total number of words in the negative review.
* Positive_Review: Positive Review the reviewer gave to the hotel. If the reviewer does not give the negative review, then it should be: 'No Positive'
* ReviewTotalPositiveWordCounts: Total number of words in the positive review.
* Reviewer_Score: Score the reviewer has given to the hotel, based on his/her experience
* TotalNumberofReviewsReviewerHasGiven: Number of Reviews the reviewers has given in the past.
* TotalNumberof_Reviews: Total number of valid reviews the hotel has.
* Tags: Tags reviewer gave the hotel.
* dayssincereview: Duration between the review date and scrape date.
* AdditionalNumberof_Scoring: There are also some guests who just made a scoring on the service rather than a review. This number indicates how many valid scores without review in there.
* lat: Latitude of the hotel
* lng: longtitude of the hotel

Data Exploration
------------------
Analyze the data features, we make the data visualiztion in these sides.
* Hotel frequency: shows the top 20 hotel that be chosen in Europe.
* Hotel location: shows the hotel distribution in different europen courtries, and show the detailed location of hotels in London.
* Review date: review date is similar to checkout date, by comparing the checkout date in 2015, 2016 and 2017, we can know the rough day that traveler's stay in the hotel.
* Reviewer's country: shows which country has the most people traveling in Europe.
* Average rating of hotel: show the average rating of hotels.
* Hotel levels: divide the hotel level based on the average rating of hotel.
* Wordcloud: display the positive words and negative words.

Data Preprocessing
-------------------
Replace the 'no negative' and 'no positive' comments with null, merge the positive and negative comments together. Justify the review sentiment by reviewer_score column.

Clean the reveiwers' comment, tokeniz words, remove stopwords and pos tag all. 

Use sentiment itensity analyzer to analyze the review sentiment, classify the sentiment to four types, neg, neu, pos and compound.

Modelling
---------
Choose two columns, clean and is_neg column. Use two methods, bag of words model and tfidf to process the text document, apply the logistic regression to train the model.  

Model Evaluation
-----------------
Evaluate the model performance, the accuracy of logistic regression is good. The difference of using bags of words and tfidf to process text is not obvious.

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

"The work I submitted represents my work and my work alone.  I abode by the academic integrity policy and I am aware of the consequences associated with engaging in academic misconduct. "

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
# jiawei
# jiawei
# appliedscienceproject
