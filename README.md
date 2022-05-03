
# Real-time Covid-19 Twitter Data Analysis

Building Real Time Data Pipeline Using Apache Flume, Apache Spark, Hadoop and MongoDB.

The coronavirus disease 2019 (COVID-19) pandemic has influenced the everyday life of people around the globe. 
In general and during lockdown phases, people worldwide use social media network to state their viewpoints and general feelings concerning the pandemic that has hampered their daily lives. 
Twitter is one of the most commonly used social media platforms, and it showed a massive increase in tweets related to coronavirus, including positive, negative, and neutral tweets, in a minimal period. 
To understand the tweets the use of sentiment analysis with the various emotions of the public toward COVID-19 due to the diverse nature of tweets. 
Meanwhile, people have expressed their feelings regarding the vaccinations' safety and effectiveness on social networking sites such as Twitter.

## Table of contents
- [Architecture](#about-the-project)
- [About the Project](#about-the-project)
  * [Tech Stack](#tech-stack)
  * [Environment Variables](#environment-variables)
- [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
  * [Run Locally](#running-tests)
- [Usage](#usage)
- [Contributing](#contributing)
  * [Code of Conduct](#code-of-conduct)
- [FAQ](#faq)
- [License](#license)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)

## Architecture
![alt text](https://github.com/AnshDesai/Covid-19-Twitter-Data/blob/master/architecture.png?raw=true)

## About the project
Streaming data integration is the foundation for leveraging streaming analytics. Specific use cases such as Fraud detection, contextual marketing triggers, Dynamic pricing all rely on leveraging a data feed or real-time data.
In many data centers, different type of servers generate large amount of data(events, Event in this case is status of the server in the data center) in real-time.

There is always a need to process these data in real-time and generate insights which will be used by the server/data center monitoring people and they have to track these server's status regularly and find the resolution in case of issues occurring, for better server stability.

Since the data is huge and coming in real-time, we need to choose the right architecture with scalable storage and computation frameworks/technologies.

Hence we want to build the Real Time Data Pipeline Using Apache Kafka, Apache Spark, Hadoop, PostgreSQL, Django and Flexmonster on Docker to generate insights out of this data.

The Spark Project/Data Pipeline is built using Apache Spark with Scala and PySpark on Apache Hadoop Cluster which is on top of Docker.

## Tech Stack

#### Source of data:
Different type of servers generate large amount of data(events, here in this case are gathered in realtime using Twitter API).
* Twitter API

#### Data Ingestion:
Since the data is huge and coming in real-time, we need to choose the right architecture with scalable storage and computation technologies.
* Apache Flume
* Apache Kafka

#### Data processing:
We use apache spark unified streaming framework for all data processing tasks( including machine learning, SQL operations) on live data streams.
* Apache Spark 

#### Database:
* MongoDB

## API Reference

#### Twitter API

Create an app named on the Twitter API website. 
This will give you the keys that you need to use the Twitter API.
Here is how to create Twitter developer API.

#### 1.1 Generating Twitter API Keys
If you don’t have developer access, go to https://dev.twitter.com/apps/new and apply for a Developer access.

#### 1.2. Creating new application
Go to https://developer.twitter.com/en/apps and Create a new application. (Leave callback URL blank)

#### 1.3. Copy the consumer keys for future reference
Go to keys and tokens tab and copy the consumer key and secret pair to a file for later use.

#### 1.4. Getting secret access keys 
Click on “Create” to generate access token and secret. Also, copy both keys to a file for later use.


| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `consumerKey` | `string` | **Required**. Your consumer API key |
| `consumerSecret` | `string` | **Required**. Your consumer-secret API key |
| `accessToken` | `string` | **Required**. Your access API key |
| `accessTokenSecret` | `string` | **Required**. Your access-secret API key |



## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`HADOOP_HOME`

`JAVA_HOME`

`SPARK_HOME`
## Getting Started
### Prerequisites
* Python 3.7 or later
* Apache flume
* Apache kafka
* MongoDB

### Installation
* Run this command to install python pakages
    ```bash
    pip freeze > requirements.txt
    ```    
* Apache Kafka
    1. Download latest version of [Apache kafka.](https://kafka.apache.org/downloads)
    2. Go to the Kafka directory.
    3. Run zookeeper using command:  
    ```bash
    nohup bin/zookeeper-server-start.sh config/zookeeper.properties > ~/zookeeper-logs &
    ```
    4. Run Kafka using the command: 
    ```bash
    nohup bin/kafka-server-start.sh config/server.properties > ~/kafka-logs &
    ```
* Apache flume
    1. Download latest version of [Apache flume.](https://flume.apache.org/download.html)
    2. Go to the Flume directory (For example, cd apache-flume-1.9.0-bin/)
    3. Run flume agent using the command: 
    ```bash
    bin/flume-ng agent --conf conf --conf-file "/home/ubuntu/flume_twitter_to_kafka.conf" --name agent1
    ```

* Apache Spark Streaming

    1. Download [spark-streaming version 2.4.5](https://spark.apache.org/streaming/)
    2. Unzip the tar file in the local workspace.
    3. Set this directory path as SPARK_HOME in environmental variables.
    4. Set the same path as HADOOP_HOME in environmental variables.
    5. Add SPARK_HOME/bin to the PATH variable.
    6. Make sure JAVA_HOME is set to JDK version 1.8
    7. Download the spark-streaming-kafka-assembly_2.11-1.6.0.jar file in this project to the local workspace
    8. Use the following example command to run: 
    ```bash
    bin\spark-submit --jars spark-streaming-kafka-assembly_2.11-1.6.0.jar D:\SparkStreaming\spark-kafka.py 3.22.26.9:9092 twitter_stream_new D:\tweets.txt
    ```


## Running Tests

To run tests, run the following commands.
#### Ignore steps 1-3 if already completed while installation:
  1. Create Twitter API account and get keys and edit twitter_config.py.
  2. Start zookeeper
  ```bash 
  \bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
  ```
  3. Start Apache Kafka
```bash  
bin/kafka-server-start.sh config/server.properties 
```
  4. Create Kafka topic
  ```bash
  kafka-topics.bat --zookeeper 127.0.0.1:2181 --create --replication-factor 1 --partitions 1 --topic BigData  
```
5. Run Apache flume
```bash
flume-ng agent -n TwitterAgent -f C:\apache-flume-1.9.0-bin\conf\twitter_config.conf
```




## Examples

```javascript
import Component from 'my-project'

function App() {
  return <Component />
}
```


## Contributing

Contributions are always welcome!

See `contributing.md` for ways to get started.

Please adhere to this project's `code of conduct`.


## FAQ

#### Question 1

Answer 1

#### Question 2

Answer 2


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Authors

- [@AnshDesai](https://www.github.com/AnshDesai)


## Acknowledgements

 - [Real-Time Data Analytics Framework for Twitter Streaming Data](https://ieeexplore.ieee.org/document/8029342)
 - [Twitter Sentiment Analysis in Real-Time](https://monkeylearn.com/blog/sentiment-analysis-of-twitter/)

## Feedback

If you have any feedback, please reach out at anshdesai20@gmail.com

