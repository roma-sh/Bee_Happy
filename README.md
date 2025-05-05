# Bee happy: Digital Beehive IoT Project

![beehive](https://github.com/roma-sh/Bee_Happy/blob/master/assets/beehive.jpg)

## Overview

This project is designed to build a complete IoT data pipeline. The system collects sensor data from multiple LoRaWAN-enabled devices (e.g., environmental sensors on a digital beehive), processes it via an IoT platform, and stores it in a PostgreSQL database for further analysis.

The main goals of this project are:

Retrieve live data from IoT sensors connected through The Things Network (TTN).

Forward and store the data in a structured PostgreSQL database.

Build a REST API service to serve the stored data.

Set up a scheduler to fetch and save data at regular intervals.

## Key Components

LoRaWAN Sensor Setup
The sensors are connected to TTN and configured to send environmental data (temperature, humidity, light intensity, pressure, and more). Each sensor group is identified by a unique authorization group name.

API Connection
Data is accessed through the IoT platform API provided by SmartCity Heilbronn. The script securely connects using API keys stored in environment variables.

Database Setup
A PostgreSQL database (BeHappy_db) is created to store all incoming sensor data. The schema will include tables for temperature, humidity, and other sensor metrics to enable efficient querying and analysis.

STACKIT Portal & Postgres
The database is hosted using the STACKIT portal, where services and access credentials are managed securely.

## How It Works

The script connects to the API endpoint based on the chosen sensor group (three available groups in this phase).

It retrieves JSON data that includes multiple environmental readings.

The script parses the JSON, extracts relevant metrics (e.g., temperature, humidity, wind speed), and prints the results to the console for real-time visibility.

Data is inserted into the database, currently focused on storing temperature values, with plans to extend the schema for additional metrics.


## Current Status

Implemented the basic data-fetching script with error handling.

Successfully established a connection to the database and inserted temperature data.

Printed sensor readings to the console for monitoring.

## Next Steps

Design and create a complete PostgreSQL schema to handle all sensor data fields (e.g., humidity, pressure, light intensity, etc.).

Extend the code to insert all retrieved data into the appropriate database tables.

Develop a REST API service that can serve stored data on demand.

Set up a scheduler (e.g., using cron jobs or APScheduler) to fetch and store data at set intervals automatically.

## Environment Variables

To keep the project secure, API keys and database credentials are stored in a .env file. The following environment variables are required:

API_KEY

DB_PASSWORD

Example .env file:

```
API_KEY=your_api_key_here
DB_PASSWORD=your_db_password_here
```

**Note:**  if you are a 42 Student you can contact me for the API key. 


## Project Vision

This project aims to create a scalable, modular, and maintainable system that not only collects and stores sensor data but also provides an API interface for external use cases, such as data visualization, environmental monitoring dashboards, or smart city integrations.