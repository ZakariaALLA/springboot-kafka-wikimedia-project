# Spring Boot Kafka Wikimedia Project

A demo project illustrating how to use Spring Boot and Apache Kafka to stream Wikimedia “recent changes” events into a Kafka topic, and then consume and persist those events into a database.
The link of Wikimedia API is [here](https://stream.wikimedia.org/v2/stream/recentchange).

## Project Modules

This multi-module Maven project contains two sub-modules:

- **kafka-producer-wikimedia**  
  A Spring Boot application that connects to Wikimedia’s EventStream API (recent changes stream) and publishes each change event to a Kafka topic (default: `wikimedia.recentchange`).

- **kafka-consumer-database**  
  A Spring Boot application that consumes messages from the `wikimedia.recentchange` topic and writes selected fields into a PostgreSQL database.

## Prerequisites

- Java 21
- Maven 3.8+
- Kafka & Zookeeper
- PostgreSQL

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/ZakariaALLA/springboot-kafka-wikimedia-project.git
cd springboot-kafka-wikimedia-project
```

### 2. Import the project in your IDE
For IntelliJ IDEA, open the `pom.xml` file and select "Import as Maven Project". Let IntelliJ download the necessary dependencies.

### 3. Start Zookeeper and Kafka
Install kafka and start it locally. You can follow the instructions from the [Kafka Quickstart](https://kafka.apache.org/quickstart).

### 5. Create the PostgreSQL database
Create a PostgreSQL database using the following command:
```sql
CREATE DATABASE wikimedia_db;
```

### 5. Run the applications
- Run the `kafka-producer-wikimedia` application to start producing messages to the Kafka topic.
- Run the `kafka-consumer-database` application to start consuming messages from the Kafka topic and writing them to the PostgreSQL database.

