## Course Link

[Apache Kafka Series - Learn Apache Kafka for Beginners v3](https://www.udemy.com/course/apache-kafka/?couponCode=ST1MT31025G3)

## Installation 

### Download

[Download Kafka](https://kafka.apache.org/downloads)

### Setup

[Setup Kafka on Mac](https://learn.conduktor.io/kafka/how-to-install-apache-kafka-on-mac/)

1. Edit zshrc file:
    ```sh
    vi ~/.zshrc 
    ```
2. Set path variable:
    ```sh
    export PATH="$PATH:/Users/gandharvpathak/kafka_2.13-3.9.0/bin"
    ```

## Commands

### Start the Zookeeper server:
```sh
zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties
```

### Start the Kafka server:
```sh
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties
```

### Alias commands:
```sh
start-zookeeper # starts zookeeper server
start-kafka # starts kafka server
create-kafka-topic test-topic --partitions 1 --replication-factor 1 # creates topic
list-kafka-topics # lists all kafka topics
```

### Create Kafka topic:
```sh
kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test --partitions 1 --replication-factor 1
```

### Delete Kafka topic:
```sh
kafka-topics.sh --bootstrap-server localhost:9092 --delete --topic <topic_name>
```

### Alias command:
```sh
create-kafka-topic test-topic --partitions 1 --replication-factor 1 
```

## Send data using Kafka console producer:
```sh
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test < /Users/gandharvpathak/workspace/kafka/kafka/sample.csv 
```

## Read data using Kafka console consumer:
```sh
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```
