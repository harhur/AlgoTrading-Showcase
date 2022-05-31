# AlgoTrading-Showcase
#### Summary, learnings, and technical design of my personal project.
#### [**Sequence Diagram**](https://github.com/harhur/AlgoTrading-Showcase/blob/main/sequence_flow.md)

<br>

## Purpose -- why did I make this?
I have always had an interest in financial data and to me, the possibilities of the stock market are endless. After completing my AWS Solutions Architect certification, I wondered about potential passion projects that could leverage AWS’ systems. This ultimately led to the creation of the AlgoTrading project. Note, There is also no freely available API that provides technical analysis on options data.

## What is it? What does it do?
The AlgoTrading program is a personal project that I developed over the past few months. It is able to scan thousands of option contracts live on the market and notify me of trades that are highly likely to be profitable. 

## How does it work?
The bread and butter of the program is a Python executable that leverages 3rd-party APIs to fetch historical and live option contract data. Through rigorous and continual parameter testing, I have arrived at a successful combination of technical analysis values that have worked well in current market conditions. The project executable is hosted on an Amazon EC2 T3.micro instance and uses a cron job to schedule a run during market hours. A Redis database stores the trades made so far and their associated data. Additionally, a host of other technologies are used that can be found in the Technologies section below.

## Features
* Send an SMS text via Twilio for promising trades
* Able to scrape hundreds of tickers from Finviz using Scrapy 
* Intelligently proxies API calls using AWS API Gateway and random client data generation
* Leveraged the requests_ip_rotator library and pair-programmed with the library’s developer to debug an issue I was having
* Integration with Yahoo Finance and Robinhood APIs to fetch data
* Dynamically fetches the relevant historical data
  * Ie skipping over weekends and holidays, shorter market days, etc.
* Uses Boto3 and multiprocessing to quickly clean up AWS resources, namely usage plans and REST APIs
* Resiliency via robust error handling and AWS Auto Scaling Group
* And the magic behind it all -- a ton of customized, under-the-hood financial analysis using analytics libraries

## Technologies and Skills Developed
* AWS
  * EC2
    * Setting up a Python Virtual Environment and creating a Python executable in a Linux environment
  * AMIs
  * Auto Scaling Group
  * API Gateway
  * Security Groups
* Deployment to the cloud
* Redis
* Twilio
* Integration with third-party APIs
* Financial skills
* A host of Python packages
  * Scrapy
  * TA-Lib
  * Pandas
  * Numpy
  * And more

## Challenges - what were they, and how did I overcome them?
* Data wrangling and validation
  * Real-world data is quite often very messy
* Deployment to the cloud
  * Initially tried using Azure with a Windows executable, but EC2 has better documentation and it was overall faster to host a Linux executable instead
* Issues with libraries
  * Stack overflow
  * Pair-programmed with the author of a library!

## Project Screenshots
![Potential Candidates](https://github.com/harhur/AlgoTrading-Showcase/blob/main/showcase.PNG)
![Backtest Analysis](https://github.com/harhur/AlgoTrading-Showcase/blob/main/showcase-2.PNG)
