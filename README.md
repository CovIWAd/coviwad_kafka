# Coviwad - Kafka 

Kafka configuration used to launch kafka with docker for CovIWAd

## Setup kafka with docker

Run docker-compose configuration:
`docker-compose -f docker-compose.yml up -d`

Access to the shell of kafka:
`docker exec -it kafka /bin/sh`

Check if your topic exist:
`cd opt/kafka`
`./bin/kafka-topics.sh --list --zookeeper zookeeper:2181`

If you don't find the topic, create it:
`./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic geolocation_topic`
