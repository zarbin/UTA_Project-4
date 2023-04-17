# Project-4 - Crypto Data, Sentiment and Signals


## Purpose: 
Cryptocurrencies have become numerous a major economic phenomenon. This project aimed to look to see if cryptocurrencies are an attractive investment at this time given economic indicators and sentiment. Do to data and time constraints, the primary cryptocurrency of focus was Bitcoin (BTC). Some specific questions we sought to answer:
1. Can we predict whether over the next 50 days BTC will outperform it’s median historic return (and how does it’s performance and predictability compare to a sample of alternative investments) use historical trading data, sentiment analysis, and various economic indicators to train ML models?
2. Does sentiment toward cryptocurrencies in the media correlate with their market price?
3. Can we create a text sentiment analysis machine learning model specifically geared toward crypto news headlines? 


______________________________________________________________________________
## Methodology:
### Project Directory Layout

    ├── Production              # datasource .csv from Kaggle and JSON files stored here for endpoints.
    │   ├── Resources           # Files for Database Import
    │   │   ├── Images          # Project Images
    │   ├── Tableau             # Tableau master workbook
    ├── Sandbox                 # sandbox environment for EDA, testing, data wrangling.
    │   ├── JennS               # Sandbox / Working files - Jenn.
    │   ├── JustinB             # Sandbox / Working files - Justin.
    │   ├── Tableau             # jSandbox / Working files - John & Joe.
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

### Tools and Packages:
* Python
* Tableau
* SQLltie

______________________________________________________________________________
## Analysis

## Contributers

- Jennifer Shulyak
- Joe Moreno
- John Quinn
- Justin Bernier
- Michael Raminki
