
## Bitcoin Twitter Sentiment and Return Prediction using Machine Learning


<img src="https://user-images.githubusercontent.com/101296133/179403202-3b827570-066b-48c5-b70c-6afab4d1bce6.png" width="500" height="500" />


- Executive Summary   
- Hypothesis / Problem stating   
- Methodology  
- Cleaning and Preprocessing techniques  
- EDA
- Machine Learning Modeling  
- Results from the model and Classification report
- Learning, Limitations and Further analysis

### Executive Summary  
The project aims to analyze the sentiment of Bitcoin tweets extracted from twitter using Natural Processing Language tools. The second part aims to use classification Machine Learning models and NLP tools to predict the intra-day returns of Bitcoin using tweets. 

The study on Bitcoin sentiment tweet through 'polarity' and 'subjectivty' models illustrates that a greater distribution of the tweets are skewed towards a positive sentiment and are more subjective in nature rather than factual based. Furthermore, the use of wordcloud supports the subjective sentiment narrative amongst twitter users. 

Results illustrates that using Logistic Regression using NLP TF-IDF provided the highest test and CV score. With the score marginally > baseline accuracy.
The classification report illustrates a highr precision score than the test and baseline score, with a significantly larger recall score.

As a conclusion, using machine learning models provide a marginal increase in both the accuracy score and precision score. However, a high recall score would indicate that further analysis can be performed to whether a study can be done on diversification in portfolio theory given the recall value minimizes false negatives. 

### Hypothesis:

_Hypothesis 1: Bitcoin twitter sentiment analysis using NLP_  
_Hypothesis 2: Using machine learning classification models to predict Bitcoin returns_

### Methodology
- The study uses approximately 6 months of tweets obtained from twitter during the period 2021-02-05 to 2021-09-10. 
- The df tweets will be merged with a df that contains a computed binary classification of daily Bitcoin returns. 
- The overall dataset will have 500,000 observations in sentiment analysis and 15,000 for the machine models. 
- Python tools: Pandas, NumPy, Regex and Scikit-learn, Textblob, NLTK, datetime, wordcloud. 
- Machine learning models: Logistic regression and Random Forest: TF-IDF vectorizer and count vectorization.

### Cleaning and Preprocessing tweets
Building Regular Expression functions for the data cleaning framework used upon special characters, hyperlinks, numerical values, and unicode for the Bitcoin tweets. The tweets were reprocessed using NLTK library 'stop words' and 'custom stop words'. 

The daily Bitcoin returns is computed by division of the change in the open and close price then applying a function to classify the returns as a binary classification (1 = positive return) and (0 = negative return).

### Hypothesis 1: Bitcoin sentiment analysis using NLP (EDA)
To analyse the Bitcon Twitter sentiment, the study used the textblob library to return the 'polarity' and 'subjectivity' of Bitcoin tweets. 
The results indicate that a greater distribution of the tweets are skewed towards a positive sentiment and are more subjective in nature rather than factual or objective based. 

<img src="https://user-images.githubusercontent.com/101296133/179405141-127ed5e4-0b4a-4130-9878-1c5f5a230850.png" width="400" height="300" />

The results are in line with word cloud findings, as words such as ‘good’ and ‘great’ are most commonly used and are subjective - positive sentiment. 
Furthermore, the word cloud gives us a feel of what Cryptocurrency topics are most spoken within the community such as 'airdrop'.

<img src="https://user-images.githubusercontent.com/101296133/179403508-fdfd52a7-a13c-46f0-be77-565519c1c6a2.png" width="600" height="400" />

### Hypothesis 2:Using machine learning classification models to predict Bitcoin Returns
The study focuses on using a Logistic Regression and Random Forest model.
The data undergoes a training - test split then fitted the data using TF-IDF vectorizer and Count Vectorization. 

<img src="https://user-images.githubusercontent.com/101296133/179405678-814ec80c-5768-4b34-8ff4-2815a61fab6e.png" width="900" height="200" />

- Target variable: Bitcoin returns 
- Independent variable: Bitcoin tweets 

The main metrics computed: test score, cross validation score and classification report scores.

#### Results of the Machine Learning model and Classification report

<img src="https://user-images.githubusercontent.com/101296133/179403639-823e2a2e-771e-4dd3-ae08-2e2a1efe755a.png" width="700" height="300" />

A logistic regression model - TF-IDF vectorization gave the best test score relative to other models at 0.64, illustrated we are 64% of the time accurately predicting Bitcoin return classified as 1. However, the test score is marginally higher than the baseline accuracy of 0.63. 

The classification report below illustrates a precision score and recall score of 0.64 and 0.91, respectively. If we were to invest in only Bitcoin, precision score would be the best metric because we would like to minimize negative returns. In regards to the higher recall score, we can afford to miss a few profitable opportunities thus the recall score is not an important relative to the precision score. 

_Findings_: Precision score > test score (cv score) > Baseline accuracy

###  Learning, Limitations and Further analysis

_A lack of influential usernames in the data_: The study did not scrape tweets from influential usernames in the Cryptocurrency community such as Vitalik Buterin, Gavin Wood, Elon Musk. A further study could be done on the impact of tweets from higher prolific individuals could possibly lead to an upward revision in the accuracy score of the models given their influence on market prices.  

_Cryptocurrency and portfolio diversification_: The logistic regression - TF-IDF model resulted in a higher recall score than the precision score. The study is based on a single asset (Bitcoin) and thus a higher precision score would be more important to ensure that the trades taken will result in a positive return and minimize being wrong. 

Due to the higher recall score, the model accurately predicts the positive return class from all the data. From a trading perspective this could insinuate that further studies can be done on portfolio diversification, whether on average diversification on multiple cryptocurrency assets can lead to higer average returns using tweets. 


_Intra-day trading_: The model takes into account on tweets released for an intra-day trading perspective rather than a long-term or daily approach to investing.

_Limits tweets as the only feature variable_: The study does not intend to find the optimal combination of several factors that predict Bitcoin returns but rather independently focuses on the impact of only tweets. Thus, it is expected for tweets to explain a smaller contribution to the accuracy on the predictability in Bitcoin returns.
