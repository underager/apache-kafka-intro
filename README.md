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