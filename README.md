# Project-4 - Crypto Data, Sentiment and Signals


## Purpose: 
Cryptocurrencies have become numerous and major economic phenomena. Media from newsites, twitter, celebrities, and billionaires have sought to encourage and discourage interest in the new forms of currency. 

This project aimed to answer if cryptocurrencies are an attractive investment at this time given economic indicators and sentiment. Due to data and time constraints, the primary cryptocurrency of focus was Bitcoin (BTC). Some specific questions we sought to answer:
1. Can we predict whether over the next 50 days BTC will outperform it’s median historic return (and how does it’s performance and predictability compare to a sample of alternative investments) use historical trading data, sentiment analysis, and various economic indicators to train ML models?
2. Does sentiment toward cryptocurrencies in the media correlate with their market price?
3. Can we create a text sentiment analysis machine learning model specifically geared toward crypto news headlines? 


______________________________________________________________________________
## Methodology:
### Project Directory Layout

    ├── Production              # Datasource .csv from Kaggle and JSON files stored here for endpoints.
    │   ├── Resources           # Files for Database Import
    │   │   ├── Images          # Project Images
    │   ├── Tableau             # Tableau master workbook
    ├── Sandbox                 # Sandbox environment for EDA, testing, data wrangling.
    │   ├── JennS               # Sandbox / Working files - Jenn.
    │   ├── JustinB             # Sandbox / Working files - Justin.
    │   ├── Tableau             # Sandbox / Working files - John & Joe.
    │   ├── mike                # Sandbox / Working files - Mike.    
    ├── LICENSE
    └── README.md               # Readme File

### Flow Chart
![image](https://user-images.githubusercontent.com/36682023/232347548-e0b19190-f126-4d04-bf5c-0e2957914b5e.png)

### Database - Market_Data.db tables
![image](https://user-images.githubusercontent.com/36682023/232348057-13307465-9878-47f0-b855-5e97f691b550.png)
[Google Sheet](https://docs.google.com/spreadsheets/d/1boIk5OkkzzumndtRMwkkKE1grw_CWv3P7WuklKdLLLw/edit?usp=sharing)

### Data Sources:

* Elon Musk Tweets (2010-2022): https://www.kaggle.com/datasets/ayhmrba/elon-musk-tweets-2010-2021?select=2021.csv 
* Elon Musk Tweets (2022-2023): https://www.kaggle.com/datasets/gpreda/elon-musk-tweets
* Banking and Crypto News Snapshots: NewsAPI - https://newsapi.org/
* Crypto Data: Coingecko API - https://www.coingecko.com/en/api
* Economic and Finance Data: yFinance Python Library - https://pypi.org/project/yfinance/
* Gallup Polls - https://news.gallup.com/poll/1597/confidence-institutions.aspx
* U.S. Bureau of Labor Statistics - https://www.bls.gov/regions/mid-atlantic/data/consumerpriceindexhistorical_us_table.htm
* GDP: Macrotrends - https://www.macrotrends.net/countries/USA/united-states/gdp-gross-domestic-product
* Surveys of Consumers - http://www.sca.isr.umich.edu/tables.html

### Text Sentiment Analysis: Vader
    * Vader (Valence Aware Dictionary and sEntiment Reasoner) was used to quantify the sentiment and determine the polarity (negative, neutral, or positive) of news headlines and tweets authored by Elon Musk concerning cryptocurrencies. 
### Text Sentiment Analysis: Random Forest Algorithm
    1. Dataset of Financial News headlines that was prelabeled with polarity was taken from Kaggle.
    2. Feature Engineering: headline length, punctuation %, and capitalization % were calculated for each headline.
    3. Data cleaning: Punctuation was removed, all text was made lowercase, stopwords were removed, a portstemmer was applied, and the data was tokenized. 
    4. Vectorization: Count and TF-IDF were tested.
    5. GridsearchCV was used to determine the optimal parameters.
    6. Model was trained using optimal parameters and a confusion matrix was procurred. Vader was used on the training data and a confusion matrix was procurred to compare the two models. 
    7. The model and vader were both applied to a new dataset: An unlabeled dataset of newsheadlines about Bitcoin (BTC) from the last month. Their results were compared.  
______________________________________________________________________________
## Analysis:
### John: 

Created a summary analysis of marketdata.csv, which contained a summary of financial categories. The other Analysis done was pulled from a crypto datasource,           which had 2 dashboards to show the upward trend of the crypto market as a whole.

![image](https://user-images.githubusercontent.com/36682023/232646098-c9469bce-4625-4718-bdf6-b5b136461238.png)


### Justin: 

Bitcoin price predections seemed very trend focused, which makes sense as the Bitcoin price history was the primary feature of the LSTM RNN. 
I'm happy awith the Mean Squared Error of .000733 and to see the regression convergence over time. 

![image](https://user-images.githubusercontent.com/36682023/232645339-38a9528a-46a3-4417-bc38-b0b7a387bd8d.png)

Bitcoin price predictions below.  Please note this is not invesment advice!  :) 

![image](https://user-images.githubusercontent.com/36682023/232647677-99e19463-dc5b-441c-8386-6f8b75e708d4.png)

Crypto Dashboard focusing on trend of Price, Volume, and Market cap for some of the top coins in the market. 

![image](https://user-images.githubusercontent.com/36682023/232647618-1b686406-626a-4f98-b439-d107ea26f95e.png)


### Sentiment and the Market: (JOE)

We took a look at some of the trends of bitcoin and the sentiment around Bitcoin over the last 3 years. We found that the sentiment on Bitcoin fluctuates depending on certain world events. The price of Bitcoin peaked late 2021 but then saw a significant decrease post-COVID and other factors that included rising inflation. However, taking a look at recent treads on price and sentiment show that Bitcoin did survive a crypto winter and is on an upward trend to start 2023 as it started around 16.6K and has hit 30K as of a few days ago. Considering the banking crisis and the failure of SVB, this indicates that the sentiment around bitcoin and the price is currently on an upward trajectory.

![image](https://user-images.githubusercontent.com/36682023/232663998-6705abc1-9a50-45ce-9954-baff7177e64f.png)

### Text Sentiment Analysis: Random Forest Algorithm
    * Optimal parameters found: depth of None and n_estimators = 300 and gave an mean_test_score of .667
    * TF-IDF was slightly more succesfully (an additional .5 in mean accuracy)
    
    ![Screen Shot 2023-04-16 at 7 48 34 PM](https://user-images.githubusercontent.com/111457464/232354068-b8c05b85-d2b6-497b-8083-bce9590280bd.png)
    
    ![Screen Shot 2023-04-16 at 7 50 15 PM](https://user-images.githubusercontent.com/111457464/232354189-30acc8c1-1fdf-4979-85a2-e0dbf905f523.png)
    
    * Despite performing better on the training data, the Random Forest NLP proved to favor labeling headlines as neutral and did so on the BTC headlines dataset. Upon inspection, Vader more accurately predicted what the team identified as being positive headlines while the Random Forest NLP labeled them as neutral. For Example: “Why Bitcoin Miner Stocks Soared This WeekBitcoin mining company stocks have soared this week, amplifying the gains of Bitcoin itself…." was labeled as "neutral" by the RF NLP and "positive" by Vader.
    * Conclusion: Until more fine tuning can be done on the Random Forest Algorithm, Vader should be used for sentiment analysis.

### Mike: 

![image](https://user-images.githubusercontent.com/36682023/232664241-f3dc2202-49ff-4a22-a95e-c09fb14e1c58.png)

![image](https://user-images.githubusercontent.com/36682023/232664266-a0b34fb4-cc59-491e-b4a4-011dceef78c7.png)



______________________________________________________________________________
## Contributers

- Jennifer Shulyak
- Joe Moreno
- John Quinn
- Justin Bernier
- Michael Raminki
