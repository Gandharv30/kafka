## Course Link
https://www.udemy.com/course/apache-kafka/?couponCode=ST1MT31025G3

Apache Kafka Series - Learn Apache Kafka for Beginners v3


## Installation 

### Download link: https://kafka.apache.org/downloads


### Setup : https://learn.conduktor.io/kafka/how-to-install-apache-kafka-on-mac/

#### 1. edit zshrc file :  
    ```vi ~/.zshrc ```
#### 2. set path variable: 
        ```export PATH="$PATH:/Users/gandharvpathak/kafka_2.13-3.9.0/bin"```

## Commands

### Start the zookeeper server :
```
zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties
```
### Start the kafka server :
```
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties
```