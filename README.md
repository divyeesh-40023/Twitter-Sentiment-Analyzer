# Twitter Sentiment Analyzer

A Python command-line application that searches recent public tweets for a keyword and analyzes their sentiment using TextBlob.

## Features

- Authenticate with the Twitter API through Tweepy
- Prompt for a search keyword and the number of tweets to analyze
- Classify tweets as positive, negative, or neutral
- Calculate the percentage of each sentiment
- Display a pie chart using Matplotlib
- Print an overall polarity-based sentiment summary

## Technologies

- Python
- [Tweepy](https://www.tweepy.org/) — Twitter API access
- [TextBlob](https://textblob.readthedocs.io/) — sentiment analysis
- [Matplotlib](https://matplotlib.org/) — pie-chart visualization

## Requirements

- Python 3
- Twitter/X API credentials
- The following Python packages:

```bash
pip install tweepy textblob matplotlib
```

TextBlob may also require its language data:

```bash
python -m textblob.download_corpora
```

## Configuration

Before running the application, replace the placeholder API credentials in `main.py` with your own credentials:

```python
consumer_key = "YOUR_CONSUMER_KEY"
consumer_secret = "YOUR_CONSUMER_SECRET"
accessToken = "YOUR_ACCESS_TOKEN"
accessTokenSecret = "YOUR_ACCESS_TOKEN_SECRET"
```

> ⚠️ **Security notice:** Never commit live API credentials to a public repository. Rotate any credentials that have already been exposed and prefer environment variables for new development.

## Usage

1. Clone the repository:

```bash
git clone https://github.com/nikhilsankhla/Twitter-Sentiment-Analyzer.git
cd Twitter-Sentiment-Analyzer
```

2. Install the dependencies:

```bash
pip install tweepy textblob matplotlib
python -m textblob.download_corpora
```

3. Run the program:

```bash
python main.py
```

4. Enter a keyword and the number of tweets when prompted:

```text
Enter Your Keyword Which you want to search
python
Enter how many you want to analyze
100
```

## How It Works

The application:

1. Authenticates with the Twitter API using OAuth.
2. Searches English tweets matching the requested keyword.
3. Creates a `TextBlob` object for each tweet.
4. Adds the polarity score to the appropriate positive, negative, or neutral category.
5. Converts each category into a percentage of the requested tweets.
6. Prints the overall polarity and displays a Matplotlib pie chart.

The sentiment categories are determined by TextBlob polarity:

- Polarity `< 0`: negative
- Polarity `= 0`: neutral
- Polarity `> 0`: positive

## Project Structure

```text
Twitter-Sentiment-Analyzer/
└── main.py    # Authentication, tweet collection, analysis, and chart output
```

## Example Output

```text
How people are reacting on python by analyzing 100 Tweets
Positive
```

The application also produces a pie chart labeled with the positive, neutral, and negative percentages.