
# **Building And Deploying A Movie Recommender System**

Content Based Recommender System recommends movies similar to the movie user likes and analyses the sentiments on the reviews given by the user for that movie.

The details of the movies(title, genre, runtime, rating, poster, etc) are fetched using an API by TMDB, https://www.themoviedb.org/documentation/api, and using the IMDB id of the movie in the API. TMDB has a rate limit of 50 requests per second.

We use *web scraping* to get the reviews given by the user in the Rotten Tomatoes site using beautifulsoup4 and performed sentiment analysis on those reviews.

This hands-on project will help you learn,
1. How to webscrape data from Wikipedia using pd.read_html()
2. How to generate Top 10 similar movie recommendations based on user searched movie by using NLP techniques like  Term Frequency - Inverse Document Frequency vectorizer and cosine similarity
3. How to deploy your solution using a Flask API
4. How to run sentiment analysis using NaiveBayes() algorithm
5. How to enhance the Flask API using html, css and javascript 
6. How to host the app in Heroku

Note - You don't need to know html, css, javascript to do this tutorial. Files are provided to you.

## Credits

This ML deployment was built following tutorials found on this [YouTube channel](https://www.youtube.com/@DataMentor)

Following updates have been made
1) Data is updated to include movies until 2023; Processing step is automated using a function
2) Added logic to hide API keys to protect sensitive info
3) Updated web scraping to get user reviews from Rotten Tomatoes since IMDB blocked web scraping
4) Got IMDB 50K Moview review data from Kaggle to train the NaiveBayes() model for sentiment analysis

## Running Flask Tests

To run a Flask deployment tests, run the following command

```bash
  python main.py
```

## Deployment

### Steps To Deploy The App:

Prepare your dataset:

        1. Data Extraction - Download data from sources provided in Jupyter notebooks; excluded due to size concerns
        2. Exploratory Data Analysis(EDA)
        3. Feature Engineering
        4. Model Building and Tuning
        5. Building Flask API
        6. Pushing code to Github
        7. Connecting to AWS EC2
        8. Deploy App

### Hiding your API Key:

You need to get your API Key here: https://www.themoviedb.org/settings/api by creating an account and requesting API access
To hide your API key in data processing notebooks, use a config.yml file to declare api_key as a variable and read it into Python using Pyyaml.
Refer to 3_DataProcessing3.ipynb to see how it is done. config.yml file is added to .gitignore to protect sensitive info.

You can create your own config.yml file and declare <your_api_key> as below
api_key: <your_api_key>

Likewise, you can use Heroku's config_vars settings to pass api_keys securely, read it in .py file using os.environ['api_key']
and pass it to the Flask's render_template() without exposing it.

For local testing before deployment, you can create your own config.js and declare <your_api_key> as below. Make sure to add it to .gitignore when you push it to GitHub.
var my_api_key ='<your_api_key>'; 

Disclaimer - This still isn't secure enough and to be 100% safe, best practices recommendation is to host a server side API that uses API Key to get the response and passes it on to client side API. I do not have enough knowledge to do this today and would love to learn from others how to do such a setup.

## GitHub Link
[Click HERE To view code](https://github.com/ArunSubramanian456/MLOPS_MovieRecommenderSystem)


### Demo
[Click HERE To view app](https://mlops-movie-recommender-sys-7befc77d3861.herokuapp.com/)

![logo](https://github.com/ArunSubramanian456/MLOPS_MovieRecommenderSystem/blob/main/app_screenshot.png?raw=true)
