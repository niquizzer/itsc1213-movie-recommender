# ITSC-1213 Movie Recommender (Semester Project)
## Description
    Purpose:
        Build a tool that allows the user to input a
        specific movie name, and output recommendations
        of movies they would like in the same genre.

    Goals:
        - Data exploration 
        - Data preprocessing
        - Data transformation
        - Train KNN algorithm
        - Create predictions
        - Display predicitions

    Non-Goals:
        - Building a crud api
        - Building a frontend
        - Building AI models

    Inputs:
        User:
            Prompt user to input top 5 movies they enjoy.

        Data:
            - credits.csv
            - keywords.csv
            - links_small.csv
            - links.csv
            - movies_metadata.csv
            - ratings_small.csv
            - ratings.csv
        
    Output:
        Produce a top 5 list of movies you should watch
        based off your input.

## Dependencies
    The project uses Anaconda to manage environments and
    dependencies. The environment can be built using the 
    environment.yml file.

    Libraries used:
        - Python 3.14
        - Pandas
        - Matplotlib
        - Numpy
        - Scikit Learn
        - ipykernel

## Data Structures
    - DataFrame: raw and cleaned movie data
    - Dictionary: movie lookup by title and ID
    - Sets: genres, keywords
    - List: users five favorite movies

    Feature DataFrame:
        movie_id | title | year | genres | keywords | cast | director

## Algorithms
    K-Nearest Neighbors (KNN) 

## Modules
    ingest.py:
        Loading data and creating DataFrame with raw data.

    clean.py:
        Data preprocessing.
        
    transform.py:
        Creating feature DataFrame.

    train.py:
        Train KNN on training data to create predictons.

    predict.py:
        KNN creates prediction.

    save.py:
        Save the results and write to user.

## Notebooks
    Uses:
        - Inspecting CSV files
        - Checking for missing values
        - Exloratory Data Analysis (EDA)
        - Testing features
        - Visualization
    
    Structure:
        01_data_exploration.ipynb
            Load movies_metadata.csv, credits.csv, and keywords.csv. Examine columns, null values, row counts, genres, and duplicate movie IDs.

        02_data_cleaning.ipynb
            Test cleaning rules interactively. For example, investigate malformed JSON-like fields, missing titles, invalid release dates, and duplicate records.

        03_feature_engineering.ipynb
            Create features from genres, keywords, cast, director, and possibly overview text. Compare options such as one-hot encoding and TF-IDF.

        04_knn_experiments.ipynb
            Test feature scaling, cosine versus Euclidean distance, and different values of k. Document why selected final approach.

        05_recommendation_demo.ipynb
            Demonstrate the complete workflow: enter a movie, find neighbors, remove the input movie itself, and display five recommendations.

    Once an approach works in a notebook, move the reusable logic into src/. The notebook should call those functions rather than contain a second, separate implementation.

    For example:
        from src.ingest import load_movies
        from src.clean import clean_movies
        from src.transform import build_features

