# Kafka Streams and KTables examples

This code is the companion of the blog post [Kafka as a coordinator](http://danlebrero.com/2018/04/09/kafka-distributed-coordination-actor-model/)

This project uses Docker to create a cluster of 3 microservices that consume from a Kafka topic using the
Kafka Streams API.

The main processing function is [here](our-service/src/our_service/run_command.clj#L33).

## Usage

Docker should be installed.

To run:

```
docker-compose up -d && docker-compose logs -f haproxy kafka1 our-service our-service2 our-service3
```

Once the environment has been started, you have to add some commands with:

```
curl --data "command-key=key1&command=open the door" -X POST http://localhost:9100/run-command
```
    
