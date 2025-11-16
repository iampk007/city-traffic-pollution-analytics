City Traffic & Pollution Analytics Platform

A complete end-to-end Data Engineering project using free APIs, Python, and cloud-native architecture (AWS/Azure optional).
This platform ingests real-time traffic and air-quality data, processes it, stores it in a warehouse, and generates insights for city planning.

🚦 1. Project Summary
This project builds a real-time + batch analytics platform for:
Road traffic congestion
Vehicle density
Air pollution (PM2.5, PM10, CO, NO2, O3)
Weather contribution
Hotspot detection
Trend analysis

You will build:
✔ API ingestion pipelines
✔ Data lake (raw + processed zones)
✔ Data warehouse models
✔ Analytics layer (dashboards + ML-ready data)

🏗 2. Architecture Diagram
        +------------------------+
        |   Traffic API          |
        +-----------+------------+
                    |
        +-----------v------------+
        |   Air Quality API      |
        +-----------+------------+
                    |
                    v
         +----------+----------+
         |     Ingestion       |
         | (Python Requests)   |
         +----------+----------+
                    |
                    v
            +-------+-------+
            |   Data Lake   |
            |  (raw zone)   |
            +-------+-------+
                    |
                    v
            +-------+-------+
            |   Processing  |
            |  (Transform)  |
            +-------+-------+
                    |
                    v
            +-------+-------+
            | Data Lake     |
            | processed zone|
            +-------+-------+
                    |
                    v
            +-------+-------+
            | Data Warehouse |
            | (DuckDB/SQLite)|
            +-------+-------+
                    |
                    v
              +-----+-----+
              | Dashboard |
              |  (PowerBI |
              |   or Web) |
              +-----------+

🧰 3. Tech Stack
Layer	Tools
Programming	Python 3.x
Storage	Local filesystem (S3 optional)
Processing	Pandas, DuckDB
Scheduling	Cron / Airflow (later week)
Visualization	Power BI / Streamlit
Version Control	Git + GitHub
🌐 4. Datasets / APIs Used
1. Traffic API

Open Source — TomTom Traffic API / MapBox Traffic / TransportAPI
(We finalize this in Week 1 Task 2)

2. Air Quality API

OpenAQ (Free)
https://docs.openaq.org/

3. Weather API

Open-Meteo (Free)
https://open-meteo.com/

📁 5. Folder Structure
project_root/
│
├── data_lake/
│   ├── raw/
│   ├── silver/
│   └── gold/
│
├── dags/
│
├── scripts/
│   ├── ingest_traffic.py
│   ├── ingest_aqi.py
│   ├── ingest_weather.py
│   ├── transform_raw_to_silver.py
│   └── transform_silver_to_gold.py
│
├── warehouse/
│   ├── create_tables.sql
│   └── load_gold_data.py
│
├── models/
│   ├── fact_city_conditions.sql
│   ├── dim_location.sql
│   ├── dim_weather.sql
│   └── dim_pollution.sql
│
├── great_expectations/
│
├── dashboards/
│
└── README.md


📝 6. How to Run the Project
git clone https://github.com/<your-username>/city-traffic-pollution-analytics
cd city-traffic-pollution-analytics
pip install -r requirements.txt
Deployed Streamlit mini portal

Final documentation
