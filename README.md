# Coviwad - Kafka 

## Setup kafka with docker

Run docker-compose configuration:
`docker-compose -f docker-compose.yml up -d`

Access to the shell of kafka:
`docker exec -it Kafka /bin/sh`

Create a topic for localisations:
`cd opt/kafka`

Check if yout topic exist:
`./bin/kafka-topics.sh --list --zookeeper zookeeper:2181`

Create the topic locations_kafka:
`./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic locations_kafka`

## Some cinfigurations
Change the duration of the topics messages (30 days):
`./bin/kafka-configs.sh --zookeeper zookeeper --alter --entity-type topics --entity-name locations_kafka --add-config retention.ms=2592000`

Change the time or retention of the server:
`cd config`
`vi server.properties`

To edit: `i`
Change the line `log.retention.hours=168 ` by `log.retention.hours=720`

To save and exit: `esc` then `x`