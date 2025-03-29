# REAL-TIME WORDCOUNT PIPELINE USING KAFKA AND PYTHON
Real-time data engineering project using Apache Kafka, Python, Airflow and Docker

## PROJECT DESCRIPTION
A real-time data engineering project that simulates streaming text input (like a book) using Apache Kafka and performs real-time word counting using Python consumers. This project demonstrates a lightweight yet powerful stream processing pipeline, perfect for showcasing fundamental data engineering skills like ingestion, transformation, and streaming analytics.

## USE CASE
Imagine a book being read line-by-line in real-time, like when a user is typing it or an audio transcription. This pipeline ingests those lines and tracks word frequency instantly which is useful for log monitoring, keyword tracking, or natural language processing (NLP) in streaming applications.

## Tech Stack
1. Kafka in KRaft mode (Bitnami image)
2. Avro serialization with Schema Registry
3. Python for the producer, consumer, and API
4. Flask for REST endpoints
5. PostgreSQL for storage
6. NLTK for stop word filtering
7. Power BI for visualization

## About this project:
I built a real-time data pipeline using Kafka, Avro, Flask, and PostgreSQL, fully Dockerized. It streams quotes from an API, filters out stop words using NLTK, counts word frequencies, and stores them in a PostgreSQL database. Then I expose the top frequent words through a REST API built with Flask, and visualize the results in Power BI.
The entire pipeline is containerized using Docker Compose, uses Kafka in KRaft mode (without Zookeeper), and supports Avro schema validation via Schema Registry.
* Streams quote text from a public API
* Produces messages into Kafka using Avro schema
* Uses a Schema Registry for validation
* Consumes data, filters stop words using NLTK
* Stores the word counts in a normalized PostgreSQL table
* Then exposes a Flask REST API for top 10 frequent words
* Power BI connects to this API to visualize real-time trends”

## Architecture:
flowchart TD
  A[🌐 Public API<br>quotable.io] -->|Quotes via REST| B[🟨 Kafka Producer<br>• Clean text<br>• Remove stopwords<br>• Avro encode]
  B --> C[🟥 Kafka Broker<br>(KRaft Mode)]
  C --> D[🟦 Kafka Consumer<br>• Avro deserialize<br>• Word counting]
  D --> E[🟩 PostgreSQL DB<br>word_count table]
  E --> F[🟦 Flask REST API<br>/top-words endpoint]
  F --> G[📊 Power BI Dashboard<br>Top 10 frequent words]

  subgraph Dockerized Microservices
    B
    C
    D
    E
    F
  end
