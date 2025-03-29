# REAL-TIME WORDCOUNT PIPELINE USING KAFKA AND PYTHON
Real-time data engineering project using Apache Kafka, Python, Airflow and Docker

## PROJECT DESCRIPTION
A real-time data engineering project that simulates streaming text input (like a book) using Apache Kafka and performs real-time word counting using Python consumers. This project demonstrates a lightweight yet powerful stream processing pipeline, perfect for showcasing fundamental data engineering skills like ingestion, transformation, and streaming analytics.

## USE CASE
Imagine a book being read line-by-line in real-time, like when a user is typing it or an audio transcription. This pipeline ingests those lines and tracks word frequency instantly which is useful for log monitoring, keyword tracking, or natural language processing (NLP) in streaming applications.

## Tech Stack
1. Apache Kafka - for real-time message streaming
2. Python - for both producer and consumer logic
3. Docker & Docker Compose - for container orchestration

## About this project:
I built a real-time data pipeline using Kafka, Avro, Flask, and PostgreSQL — fully Dockerized. It streams quotes from an API, filters out stop words using NLTK, counts word frequencies, and stores them in a PostgreSQL database. Then I expose the top frequent words through a REST API built with Flask, and visualize the results in Power BI.
The entire pipeline is containerized using Docker Compose, uses Kafka in KRaft mode (without Zookeeper), and supports Avro schema validation via Schema Registry.
