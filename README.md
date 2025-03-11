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
    This command opens the `.zshrc` file in the `vi` editor for editing.

2. Set path variable:
    ```sh
    export PATH="$PATH:/Users/gandharvpathak/kafka_2.13-3.9.0/bin"
    ```
    This command adds the Kafka binaries to your system's PATH, allowing you to run Kafka commands from any directory.

## Commands

### Start the Zookeeper server:
```sh
zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties
```
This command starts the Zookeeper server using the specified configuration file.

**Optional Arguments:**
- `--config`: Specifies the configuration file to use.

### Start the Kafka server:
```sh
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties
```
This command starts the Kafka server using the specified configuration file.

**Optional Arguments:**
- `--override`: Overrides specific configuration properties.

### Alias commands:
```sh
start-zookeeper # starts zookeeper server
start-kafka # starts kafka server
create-kafka-topic test-topic --partitions 1 --replication-factor 1 # creates topic
list-kafka-topics # lists all kafka topics
```
These alias commands simplify the process of starting the Zookeeper and Kafka servers, creating a Kafka topic, and listing all Kafka topics.

### Create Kafka topic:
```sh
kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test --partitions 1 --replication-factor 1
```
This command creates a new Kafka topic named `test` with 1 partition and a replication factor of 1.

**Optional Arguments:**
- `--config`: Specifies additional topic-level configurations.
- `--if-not-exists`: Only create the topic if it does not already exist.

### Delete Kafka topic:
```sh
kafka-topics.sh --bootstrap-server localhost:9092 --delete --topic <topic_name>
```
This command deletes the specified Kafka topic.

**Optional Arguments:**
- `--if-exists`: Only delete the topic if it exists.

### Alias command:
```sh
create-kafka-topic test-topic --partitions 1 --replication-factor 1 
```
This alias command creates a Kafka topic named `test-topic` with 1 partition and a replication factor of 1.

### Send data using Kafka console producer:
```sh
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test < /Users/gandharvpathak/workspace/kafka/kafka/sample.csv 
```
This command sends data from the `sample.csv` file to the Kafka topic named `test` using the Kafka console producer.

**Optional Arguments:**
- `--property`: Sets a property for the producer (e.g., `parse.key=true`).

### Read data using Kafka console consumer:
```sh
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```
This command reads data from the Kafka topic named `test` from the beginning using the Kafka console consumer.

**Optional Arguments:**
- `--timeout-ms`: Specifies the timeout in milliseconds.
- `--max-messages`: Specifies the maximum number of messages to read.
- `--property`: Sets a property for the consumer (e.g., `print.key=true`).
