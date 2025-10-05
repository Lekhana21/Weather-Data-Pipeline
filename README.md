
# Weather Data Pipeline - Azure Data Factory

## Overview
This project extracts daily weather data from OpenWeatherMap API, stores it in Azure Blob Storage,
and loads it into Azure SQL Database using Azure Data Factory.

## Architecture
Weather API → ADF → Blob Storage → SQL Database

## Pipeline Activities
1. Web Activity: Fetch weather JSON from API
2. Copy Activity: Store raw JSON in Blob
3. Data Flow: Flatten and transform JSON
4. Copy Activity: Load data into SQL table

## SQL Table
```sql
CREATE TABLE dbo.WeatherData (
    City NVARCHAR(100),
    Temperature FLOAT,
    Humidity INT,
    Pressure INT,
    Description NVARCHAR(200),
    ObservationTime DATETIME
);
