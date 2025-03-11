## Course Link
https://www.udemy.com/course/apache-kafka/?couponCode=ST1MT31025G3

Apache Kafka Series - Learn Apache Kafka for Beginners v3


## Installation 

### Download link: https://kafka.apache.org/downloads


### Setup : https://learn.conduktor.io/kafka/how-to-install-apache-kafka-on-mac/

#### 1. edit zshrc file :  
        vi ~/.zshrc 
#### 2. set path variable: 
        export PATH="$PATH:/Users/gandharvpathak/kafka_2.13-3.9.0/bin"

## Commands

### Start the zookeeper server :
```
zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties
```
### Start the kafka server :
```
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties
```

```
start-zookeeper # starts zookeeper server
start-kafka # starts kafka server
create-kafka-topic test-topic --partitions 1 --replication-factor 1 # creates topic
list-kafka-topics #lists all kafka topics
```

### Create kafka topic

#### Command 

```
kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test --partitions 1 --replication-factor 1
```

### Delete kafka topic
```
kafka-topics.sh --bootstrap-server localhost:9092 --delete --topic <topic_name>
```

### Alias command
``` 
create-kafka-topic test-topic --partitions 1 --replication-factor 1 
``` 

## Send data using kafka console producer

 kafka-console-producer.sh - name of the script

 bootstrap-server localhost:9092 - location of kakfa broker

 topic name  - test 

 separator - < 

 file_name - /Users/gandharvpathak/workspace/kafka/kafka/sample.csv 

```
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test < /Users/gandharvpathak/workspace/kafka/kafka/sample.csv 
```

## Read data using kafka console consumer
```
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```