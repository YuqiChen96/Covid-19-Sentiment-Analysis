# Covid-19-Sentiment-Analysis
### Yuqi Chen & Guoran Zhang

# Abstract
  COVID-19 pandemic happens on 11th March 2020 and it rapidly developed as one of the most wildly pandemic in human history. This study focuses on the sentiment analysis of tweets of the Twitter social media using Python programming language. The dataset has been collected from Twitter that contains 41157 tweets. The primary object is to use a sentiment classifier to study people’s attitudes to corona virus and predict. This report uses 7 different classification methods to predict the tweets contents and the corresponding attitudes. Results indicate that Catboost is the best model for multiclass classification with 61% accuracy and SGD is the best model for binary classification with 87% accuracy.
- Keywords— —COVID-19; pandemic; sentiment analysis; Twitter; Catboost; SGD

# Introduction
- COVID-19, Corona Virus Disease of 2019, has been stated as a pandemic by World Health Organization (WHO) on 11th March 2020. The current situation has reported that there are still more than twenty-two million people being tested positive worldwide as of 9th May 2021 [1]. People still need work remoted in many countries, self-quarantine, and keep social distance from each other to control this virus. Thus, it is critical to implement different measures to protect countries by elucidating relevant facts and information [1]. This pandemic is currently causing severe economic problems on both a national and microscale. The nations may experience economic recession since people have being restricted from traveling, and all economic activities have been closed [2]. As the end of 2020, many vaccines have been coming out through many countries especially the China and the United States of America. Many people are getting recovered after taking those vaccines in those two countries, but there is still a large amount of people in the U.S. not taking vaccines for different reasons.  
- The amount of social data on the internet is rapidly increasing these days. This allows researchers to gain access to data and information for research purposes [3]. During the global COVID-19 outbreak, many individuals and organizations have posted their thoughts on the coronavirus Twitter has been using as one of social networking sites that allows people to share information and comments during this crucial time. Many people, organizations, and even governments rely on this media to get news or post their thoughts and feelings about the issues of the pandemic.  
- Tweets are the messages that created by using Twitter. These data are freely available in the public domain [2]. Then many people can access and collect those tweets data from Twitter by using some Twitter API, but it has limits that change over time and only allows one week’s data per time. Some companies using these data to review some customers feelings and thoughts which can help them to change some of their decisions or policies, and this type of study is often called the sentiment analysis  
- With the help of natural language processing (NLP) techniques, we can create more complex discussion by using sentiment analysis, and word cloud visualizations. This study focuses on the sentiment analysis of tweets of the Twitter social media using Python programming language. The tweets have been collected, and it will be preprocessed and then used for text manipulation and sentiment analysis by using some packages such like Nltk. After the sentiment analysis, we will build a classification model to predict the sentiment of Covid-19 tweets.

# Related Work 
- Ayush Pareek uses different feature sets like unigrams, bigrams, trigrams and negation detection and machine learning classifiers to find the best combination for sentiment analysis of twitter. He also manipulates different pre-processing steps like - punctuations, emoticons, twitter specific terms and stemming methods. He trains classifier by using some different machine-learning algorithms like the Naive Bayes, Decision Trees and Maximum Entropy. He concludes that both Negation Detection and higher order n-grams are useful for the text classification and Naive Bayes Classifier performs better than Maximum Entropy Classifier. He gets the best accuracy of 86.68% in the case of Unigrams + Bigrams + Trigrams combination which is trained on the Naive Bayes Classifier [4].  
- Our most features coding and vectorization methods coding (N-grams & Negation handling) are from Ayush Pareek Github: https://github.com/ayushoriginal/Sentiment-Analysis-Twitter 

# Method
### About the data
We collect our data from Kaggle about the Coronavirus tweets. The tweets have been pulled from Twitter and manual tagging has been done then. For this project, more than 40 thousand of tweets with the "COVID-19" related keywords between March 2020 to April 2020 were fetched for the sentiment analysis. The data originally contains 6 variables – UserName, ScreenName, Location, TweetAt, OriginalTweet, and Sentiment. The ScreeNames and UserNames have been given codes to avoid any privacy concerns. The data has already split into training and testing datasets with 41157 tweets in training dataset and 3798 tweets in testing dataset. The Sentiment has been transformed into 5 types of sentiments – extremely negative, negative, neutral, positive, extremely positive. TweetAt is the time variable which indicates the time the tweets have been posted. The originalTweet is the tweet texts we want to use to perform our sentiment analysis. So in next section we will introduce our data preprocessing steps in details.   
  
### Data Preprocessing

Remove those columns that are not useful for our sentiment analysis and only keep ‘OriginalTweet and ‘Sentiment’ in the data frame. Then we remove those emoticons, urls, userhandels, stopwords, negations, and special characters.  

We use TextBlob package to visualize the sentiments with its polarity and subjectivity and count figure.  

![1](https://user-images.githubusercontent.com/54686263/117685734-305af980-b184-11eb-82bf-a7e3a2f97dbd.png) 

Most of the tweets in the dataset seem to be neutral and not much subjectivity. However, in the polar tweets, there are slightly more positively charged tweets than negatively charged tweets. We can say that covid-19 pandemic on twitter is generally optimistic, but it would be nice to see what sentiment that people’s feelings and thoughts are [10].  

![image](https://user-images.githubusercontent.com/54686263/117685977-6a2c0000-b184-11eb-8cdc-8a90aea44143.png)  

The original common words showing above include those high frequent hashtags like “COVID”, “covid-19”, and “CORONAVIRUS” etc. We tend to remove these words and only keep “coronavirus” in the list. There are some high frequent words such like “price”, “food”, “consumer”, and “pandemic” etc.  

Then we want to know that what is the common word difference between the “Positive” and “Negative” sentiment. We introduce the word-cloud map to show the comparison as figure 4 and figure 5 below. These word clouds yield similar result as the common words in figure 3. The extremely positive sentiment shows the reference words like “great”, “best”, “thank”, “hand-sanitizer”, and “free”. Moreover, the extremely negative sentiment shows the reference words like “panic”, “crisis”, and “fear” So I think it is more likely want to emphasis lots of people are experiencing the crisis period and feel panic and fear of the virus, but those people who get over the virus and get recovered are more optimal like they feel more thankful to the doctors or those vaccines that helps them recover.  

![image](https://user-images.githubusercontent.com/54686263/117686300-bb3bf400-b184-11eb-977f-0efbb4f3b543.png)  
Figure 4: WordCloud of Extremly Positive Sentiment  

![image](https://user-images.githubusercontent.com/54686263/117686316-becf7b00-b184-11eb-8ea2-4cd9d3bf9303.png)  
Figure 5: WordCloud of Extremly Negative Sentiment  

### Vectorization  




