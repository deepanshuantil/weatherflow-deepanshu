# WeatherFlow

**Author:** Deepanshu · LSA Data Engineering Internship, November 2026

## Goal

A regional events company plans outdoor work in five UK cities: London, Manchester, Birmingham, Edinburgh and Cardiff. They need hourly weather they can trust, refreshed automatically, so they can spot risky conditions before sending crews out. This project builds that data pipeline step by step. It extracts live weather from the free Open-Meteo API, saves the raw responses unchanged, transforms them into a clean hourly table, and loads them into a database that can be queried with SQL.

## Project structure

```
weatherflow-deepanshu/
├── README.md          what this project is and how to run it
├── .gitignore         files Git must never track
├── requirements.txt   Python packages and versions
├── data/              raw and processed data (ignored by Git)
├── docs/              architecture diagram, critique, data dictionary, reflections
├── notebooks/         Jupyter notebooks for exploration
└── sql/               SQL queries
```

## How to set up

Requires Python 3.11 to 3.13 and Git (some packages don't support Python 3.14+ yet).
```sh
git clone <repo-url>
cd weatherflow-deepanshu

python -m venv .venv
# Windows:   .venv\Scripts\activate
# Mac/Linux: source .venv/bin/activate

pip install -r requirements.txt
```

## How to run

*Coming in Task 1.5.* The full pipeline will run with one command:

```sh
python etl_v1.py
sqlite3 weather.db "SELECT city, COUNT(*) FROM weather_hourly GROUP BY city;"
```
