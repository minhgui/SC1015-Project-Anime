# SC1015-Project-Anime-Success
SC1015 Mini-Project


# Group Members:
- Alvin Ong Ming Hui
- Jan Cheng Jie
- Tay Zhi Xian

# Our Motivation:
As an avid anime lovers ourselves, our love for anime is at the core of wy we embarked on this project. We understand the joy and inspiration that anime brings to its viewers, and we are driven to contribute to industry that bring us joy so much. By leevraging our skills in data analysis and predictive modeling, we aim to give back to the community and industry and that have enriched our lives.


# Problem Goal
The anime industry has seen explosive growth globally, evolving from a niche culture product to a significant pillar of mainstream entertainment. This surge in popularity brings both opportunities anc challenges for creators, distributors, and marketers within the industry. As an anime lovers ourselve, our primary goal behind this Anime Classificaiton Project is to make use of the data that we extract from the famous platform called MyAnimelist and used to analyse asnd predict the success of anime series and movies, thereby informing strategic decisions that can maximise both cretaeive and commercial success. And ultimately bring top notch anime to us.
  1. Understanding Viewer Preferences and Trends: By analysing the aniem data that we extracted, we wish to identify trends and patterns that drive success. Understanding what are the viewer preferences.
  2. Predict Anime Success: We wish to use machine learning techniques like classification to help predict whether an anime can be successful or not, so that marketers and producers can better allocate their budgest and resources.


# Dataset
Extracted from MyAnimeList using Jikan API and MyAnimeList API


# Content
1. ExtractMAL.ipynb
2. DataCleaning.ipynb
3. EDA_Visualisation.ipynb
4. Anime_Classification.ipynb
5. Time_Series_Popularity_Genres.ipynb

# Slide Deck


# Summary of Our Project:
### 1. Data extraction
- Used 2 APIs (Jikan API and MAL API) to extract and merge all the data in anime_merge_final.csv

### 2. Data Cleaning & Proprocessing
  -  Handle Null Data
  -  Remove Unneccessary Row & Col
  -  Clean Special Characters
  -  Fill Season Columns
  -  Generate new columns based on existing ones
  -  Convert the source and genres cols into timeseries like dataset

### 3. EDA Visualisation
  - Anayse columns like genre, source, studio, media type, season, relationships between rank, popularity, score and the statistics features
  - Analyse Top Anime Based on Both Popularity and Rank
  - Analyse Top 100 most popular anime (only according to popularity)

### 4. Classification Machine Learning
  1. Generate target variable col - successful(1) and unsuccessful(0)
  2. Data Preprocessing and Feature Engineering
      - One-hot encode categorical data
      - Scale Numerical Features
      - Feature Selection using SelectKBest
  3. Handling Imbalance Dataset
      - Stratification
      - Talks about the con of resampling of data
      - Model-based Approaches
  4. Model Selection and Evaluation:
      - Baseline model using DummyClassifier
      - Train multiple classification models like logistic regression, Decision Tree, Ada Boosting, Random Forest, KNN, Gradient Boosting, XGBoosting, Extra Trees
  5. Hyperparameter Tuning
      - Tune the best model with parameters
      - Find the highest importance features

### 5. Time Series 
From our data processing we’ve identified some variables with potential for correlation. We’ve also identified genre as a potential variable that may help us answer our question. So, as you can see, our first approach is to use regression models with numeric data that have moderate to high correlations. The genre we will focus on is Action as there is a lot of action anime and the numeric data we will use is score, popularity and statistics_plan_to_watch as they have moderate correlation with one another.

Now, we ran through a gamut of regression models, with the best being gradient booster at 95%. As you can see, the predicted and actual data is very similar. However, if you notice that the graph itself is non linear and lacks trend or seasonality, it can be said that all we’ve done is be able to more accurately determine an existing anime’s popularity based on score and statistics_plan_to_watch. Which is not very useful, because it’s not like we can confidently say if an anime has a high score and many people plan to watch it is popular as we have no data to base this off. If such a case was true this graph would be linear in nature.

Another approach is, we looked at whether popularity over time would be able to answer our question of what determines a popular anime. However, similar to before, the data lacks seasonality or trends as the ADF fuller test shows it is non-stationary, this means it is not affected by time, which usually means models such as ARIMA and exponential smoothing will also produce unuseful data. However, for the sake of accuracy, we will proceed to see what kind of data will actually be produced for popularity over time.

As you can see, it is indeed useful. But we have learnt that for time series data, the kind of data that we would need to answer our question would have to be much more in terms of over time, for example, if we could get the score for every action anime episode and their average score or popularity per episode we will have a model that might show some semblance of use in determining future anime popularity for action genre anime rather than just the score for many individual anime series as there isn’t enough.

# References:
- https://jikan.moe
- https://myanimelist.net/apiconfig/references/api/v2
- https://www.grandviewresearch.com/industry-analysis/anime-market
- https://www.kdnuggets.com/2017/06/7-techniques-handle-imbalanced-data.html


