# Kafka-Confluent-Streaming-KSQL

## Instructions

1. Run following command in KSQL prompt:

  `RUN SCRIPT 'confluentConsumer.ksql';`

2. To view results of windowed unique user aggregation in KSQL type the following:

  `SELECT ROWKEY, UNIQUE_USERS FROM UNIQUE_USERS; To stop type:Ctrl-C:`

3. View analysis in the Control Console

4. Navigate to Development-KSQL-Query Editor

5. To view results of non windowed country counts type the following:

  `SELECT ROWTIME, COUNTRY, COUNTRYCOUNT FROM COUNTRY_AGG;`

6. Run the script below under the Producer Heading to begin the Kafka Stream

7. Once the stream has ended stop both queries and exit KSQL using the below command:

  `exit`

8. End Services by running the following script:

  `sudo ~/Documents/Oetker/./confluentStop`


## File Explanations
### confluentStart
  * install dependencies
  * install confluent
  * add to path
  * start confluent services
  * create topic
  * start ksql client

### confluenConsumer
  * USER:                Stream Created from Kafka Topic 
  * USER_INFO:           Stream Created from USER Topic
  * UNIQUE_USERS:        Table Created from USER_INFO
  * COUNTRY_AGG:         Table Created from USER Topic

## Confluent Justifications/Limitations
### Justifications
* Easy integration with kafka streaming
* UI interface for monitoring stream performance and visualizing stream analytics
* KSQL integrates well with JSON kafka stream
* Packaged Kafka Zookeeper KSQL solution

### Limitations
* KSQL doesn't allow for aggregations of aggregated table data.
* Not able to select MAX, MIN from COUNT(*) for country
* Limited functionality in syncing queries with data streams
* Still in development/beta phase
