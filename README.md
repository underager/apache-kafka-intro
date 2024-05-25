# Introduction to Apache Kafka

## Overview

- What problem does Apache Kafka solves?
- What is Apache Kafka?
- What does its Architecture comprises of?
  
### What problem does Apache Kafka solves?

- Databases have less throughput, meaning if we keep bombarding database with frequent insertion request it will go down in few seconds to minutes depending on the load of insertion request.

![Client DB Insertions](/assets/images/clientDBInsertions.png)

### How does Kafka solves this problem?

- Apache Kafka has high throughput, it can process all the incoming insertion request and then dump that data into database in a bulk fashion in single go.
- On the downside kafka does not have enough storage, so the data that is processed is stored temporarily, furthermore you cannot query the data stored in kafka.
  
  ![Client Kafka DB flow](/assets/images/clientKafkaDBFlow.png)

### What are the components of Apache Kafka?

  Kafka components could be broken down into following parts
    - Admin
    - Producers
    - Consumers
  
  ![Kafka Architecture](/assets/images/KafkaArchitectire.webp)

  The Broker can be further divided into topics, which can further be divided into partitions as shown in the following image.

    - When Producer sends a message that is related to a topic, that message is stored inside of a particular partition.

  ![Broker topics and Partitions](/assets/images/Kafka-Broker.webp)

Producer - Partition - Consumer Balancing

![ProducerPartitionConsumerBalancing](/assets/images/ProducerPartitionConsumerBalancing.png)

#### Consumer - Partition relationship

- 1 Consumer can consume from multiple Partitions.
- 1 Partition can however publish to 1 Consumer only.

![ConsumerPartitionRelationship](/assets/images/PartionConsumerRelationship.png)

![ConsumerPartitionCanAndCannot](/assets/images/ConsumerPartitionCanAndCannot.png)

### Consumer Groups

- By default a Consumer will be inside a Consumer group.

![PartitionConsumerGroups](/assets/images/PartitionConsumerGroups.png)

### Queue V/S Pub-Sub pattern

- In a Queue there is only one Publisher and One Consumer
- In a Pub-Sub pattern, for a single Publisher there can be multiple Subscribers.
- Apache Kafka, with its Consumer Groups can function as both, a Queue and Pub-Sub pattern.

![QueueAndPubSubPattern](/assets/images/QueueAndPubSubPattern.png)