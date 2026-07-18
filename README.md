# Weather Data ETL Pipeline

A basic ETL (Extract, Transform, Load) pipeline built using real-time weather data from the OpenWeather API.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [ETL Process](#etl-process)
- [Tools Used](#tools-used)
- [Project Structure](#project-structure)
- [How to Run](#how-to-run)
- [Steps Taken](#steps-taken)
- [Key Findings](#key-findings)

---

## Project Overview

This project is about building a basic ETL pipeline using real-time weather data. The idea was to pull live data straight from an API, clean it up, store it, and then pull out a few findings from it.

---

## Data Source

I used the [OpenWeather API](https://openweathermap.org/api) to get live weather data. You need a free account and an API key to use it. I collected data for 7 cities spread across different states in Nigeria, so I could get a mix of coastal, northern, eastern, and western locations:

- Lagos
- Abuja
- Kano
- Port Harcourt
- Ibadan
- Enugu
- Kaduna

---

## ETL Process

**Extract:** Connected to the OpenWeather API using Python and pulled live weather data for each of the 7 cities. This gave raw data straight from the API, including temperature, humidity, weather condition, wind speed, and the exact time it was recorded.

**Transform:** The raw data from the API is nested and messy (dictionaries inside dictionaries), so I used Pandas to flatten it into a clean table — one row per city, with proper column names and the right data types.

**Load:** Once clean, the data was saved as a CSV file so it can be opened in Excel or reused later without calling the API again.

---

## Tools Used

- Python
- Pandas
- Requests
- Visual Studio Code
- Jupyter Notebook (via VS Code)
- OpenWeather API

---

## Project Structure

```
weather-etl-pipeline/
├── Weather_ETL_Pipeline.ipynb   # Main notebook: extract, transform, load, analyze
├── weather_data.csv             # Cleaned output dataset
└── README.md                    # Project documentation
```

---

## How to Run

1. Clone or download this repository.
2. Install the required libraries:
   ```
   pip install pandas requests
   ```
3. Get a free API key from [openweathermap.org/api](https://openweathermap.org/api).
4. Open `Weather_ETL_Pipeline.ipynb` and paste your API key into the `API_KEY` variable.
5. Run all cells.

---

## Steps Taken

1. Created a free OpenWeather account and generated an API key.
2. Set up Python and VS Code.
3. Wrote the extraction step to pull live data for all 7 cities.
4. Cleaned and transformed the raw data into a proper table using Pandas.
5. Saved the cleaned data to a CSV file.
6. Ran basic analysis on the data to compare the cities.
7. Checked my findings against the full dataset before writing them down.

---

## Key Findings

Lagos was the hottest city at 24.3°C, while Abuja was the coolest at 22.29°C.

All the cities showed cloudy conditions except Lagos, which was rainy.

Kano stood out as both the least humid city (84%) and the windiest (4.17 m/s), which looked like it might point to a relationship between humidity and wind speed. Checking this across all 7 cities gave a correlation of -0.42 — a weak relationship, not a real trend.
