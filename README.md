# Kafka Project

## Course Link

[Apache Kafka Series - Learn Apache Kafka for Beginners v3](https://www.udemy.com/course/apache-kafka/?couponCode=ST1MT31025G3)

## Installation 

### Download

[Download Kafka](https://kafka.apache.org/downloads)

### Setup

[Setup Kafka on Mac](https://learn.conduktor.io/kafka/how-to-install-apache-kafka-on-mac/)

1. **Edit zshrc file**:
    ```sh
    vi ~/.zshrc 
    ```
    This command opens the `.zshrc` file in the `vi` editor for editing.

2. **Set path variable**:
    ```sh
    export PATH="$PATH:/Users/gandharvpathak/kafka_2.13-3.9.0/bin"
    ```
    This command adds the Kafka binaries to your system's PATH, allowing you to run Kafka commands from any directory.

## Commands

### Start Servers

#### Start the Zookeeper server:
```sh
zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties
```
This command starts the Zookeeper server using the specified configuration file.

**Optional Arguments:**
- `--config`: Specifies the configuration file to use.
    ```sh
    zookeeper-server-start.sh --config ~/kafka_2.13-3.9.0/config/custom_zookeeper.properties
    ```

#### Start the Kafka server:
```sh
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties
```
This command starts the Kafka server using the specified configuration file.

**Optional Arguments:**
- `--override`: Overrides specific configuration properties.
    ```sh
    kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties --override log.dirs=/tmp/kafka-logs
    ```

### Alias Commands:
```sh
start-zookeeper # starts zookeeper server
start-kafka # starts kafka server
create_kafka_topic my_topic 3 # creates topic with 3 partitions
create_kafka_topic my_topic # creates topic with default 1 partition
delete_kafka_topic my_topic # deletes topic if it exists
list-kafka-topics # lists all kafka topics
```
These alias commands simplify the process of starting the Zookeeper and Kafka servers, creating a Kafka topic, listing all Kafka topics, and deleting a Kafka topic if it exists.

### Manage Kafka Topics

#### Create Kafka Topic:
```sh
kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test --partitions 1 --replication-factor 1
```
This command creates a new Kafka topic named `test` with 1 partition and a replication factor of 1.

**Optional Arguments:**
- `--config`: Specifies additional topic-level configurations.
    ```sh
    kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test --partitions 1 --replication-factor 1 --config cleanup.policy=compact
    ```
- `--if-not-exists`: Only create the topic if it does not already exist.
    ```sh
    kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test --partitions 1 --replication-factor 1 --if-not-exists
    ```

#### Delete Kafka Topic:
```sh
kafka-topics.sh --bootstrap-server localhost:9092 --delete --topic <topic_name>
```
This command deletes the specified Kafka topic.

**Optional Arguments:**
- `--if-exists`: Only delete the topic if it exists.
    ```sh
    kafka-topics.sh --bootstrap-server localhost:9092 --delete --topic test --if-exists
    ```

#### Alias Command:
```sh
create_kafka_topic test-topic 1 # creates a Kafka topic named `test-topic` with 1 partition
delete_kafka_topic test-topic # deletes the Kafka topic named `test-topic` if it exists
```

### Data Operations

#### Send Data Using Kafka Console Producer:
```sh
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test < /Users/gandharvpathak/workspace/kafka/kafka/sample.csv 
```
This command sends data from the `sample.csv` file to the Kafka topic named `test` using the Kafka console producer.

**Optional Arguments:**
- `--property`: Sets a property for the producer (e.g., `parse.key=true`).
    ```sh
    kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test --property parse.key=true < /Users/gandharvpathak/workspace/kafka/kafka/sample.csv
    ```

#### Read Data Using Kafka Console Consumer:
```sh
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```
This command reads data from the Kafka topic named `test` from the beginning using the Kafka console consumer.

**Optional Arguments:**
- `--timeout-ms`: Specifies the timeout in milliseconds.
    ```sh
    kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning --timeout-ms 1000
    ```
- `--max-messages`: Specifies the maximum number of messages to read.
    ```sh
    kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning --max-messages 10
    ```
- `--property`: Sets a property for the consumer (e.g., `print.key=true`).
    ```sh
    kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning --property print.key=true
    ```

## Commands for Remote Broker

### Manage Kafka Topics on Remote Broker

#### Create Kafka Topic on Remote Broker:
```sh
kafka-topics.sh --bootstrap-server remote-broker:9092 --create --topic test --partitions 1 --replication-factor 1
```
This command creates a new Kafka topic named `test` on a remote broker with 1 partition and a replication factor of 1.

#### Delete Kafka Topic on Remote Broker:
```sh
kafka-topics.sh --bootstrap-server remote-broker:9092 --delete --topic <topic_name>
```
This command deletes the specified Kafka topic on a remote broker.

### Data Operations on Remote Broker

#### Send Data Using Kafka Console Producer to Remote Broker:
```sh
kafka-console-producer.sh --bootstrap-server remote-broker:9092 --topic test < /Users/gandharvpathak/workspace/kafka/kafka/sample.csv 
```
This command sends data from the `sample.csv` file to the Kafka topic named `test` on a remote broker using the Kafka console producer.

#### Read Data Using Kafka Console Consumer from Remote Broker:
```sh
kafka-console-consumer.sh --bootstrap-server remote-broker:9092 --topic test --from-beginning
```
This command reads data from the Kafka topic named `test` from the beginning on a remote broker using the Kafka console consumer.
