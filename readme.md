# How to use this container

Follow these simple steps to have a quick up and running Apache Kafka

Not recommanded for production


### start kafka container
> docker-compose up -d

Be sure to execute this command on the same path where the docker-compose file is located :
> cd ~/path/to/cloned/kafka-container


### check all containers are spinned up
> docker-compose ps 


### enter the container CLI
> docker-compose exec kafka bash

### create topics
> kafka-topics --create --topic example-topic --bootstrap-server kafka:9092 --replication-factor 1 --partitions 1

### list all topics
```
kafka-topics --list --zookeeper zookeeper:2181
```


### produce messages
> kafka-console-producer --topic example-topic --bootstrap-server kafka:9092 \
>  --property parse.key=true \
>  --property key.separator=":"

kafka-console-producer --topic example-topic --bootstrap-server kafka:9092 \
 --property parse.key=true \
 --property key.separator=":"
  

### consume messages
> kafka-console-consumer --topic example-topic --bootstrap-server kafka:9092 --from-beginning