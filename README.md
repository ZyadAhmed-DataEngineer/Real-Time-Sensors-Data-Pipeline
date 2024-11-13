# Real-Time Sensors Data Pipeline

A real-time data pipeline that processes sensor data using AWS Kinesis, Decodable, and AWS Managed Service for Apache Flink (MSF), with data ultimately stored in PostgreSQL on Neon.

## Overview

This project demonstrates a data pipeline for ingesting, transforming, and storing sensor data in real time. Simulated sensor readings (temperature, humidity, and energy) are streamed through AWS Kinesis, transformed using Decodable, and stored in PostgreSQL on Neon.

## Architecture

- **Data Producers**: Python scripts generate random sensor data (temperature, humidity, and energy) and send it to AWS Kinesis Streams.
- **AWS Kinesis Streams**: Acts as the data ingestion point, receiving data for Decodable to process.
- **Decodable Pipelines**: Connects to Kinesis, applies transformations and aggregations, and routes data through AWS MSF.
- **PostgreSQL on Neon**: Stores the processed data for analysis and visualization.

## Features

- Real-time data ingestion and processing
- Flexible data transformations with Decodable
- Scalable architecture with AWS Kinesis and Apache Flink
- Data storage in PostgreSQL for easy access

## Configuration

1. Update the `config.json` file with your AWS and PostgreSQL credentials, as well as any necessary device settings.
2. Set the stream interval and specify device IDs/types as required.

## Usage

Run the data producer script to start sending sensor data to Kinesis:

```bash
python data_producer.py
