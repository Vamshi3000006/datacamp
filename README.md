# 🗽 NYC Taxi Rides – dbt Project

## 📌 Project Overview
This repository contains a complete dbt project named **`taxi_rides_ny`** built while following along with the [DataTalksClub Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp). The focus is on modeling, documenting, and testing yellow and green taxi trip data from New York City using dbt best practices.

---

## 🚕 Project Structure
```plaintext
📁 analyses/                  → Contains custom analysis queries (e.g., hack-load-data.sq)
📁 macros/                    → Custom Jinja macros (e.g., get_payment_type_description.sql)
📁 models/
    ┣ 📁 staging/            → Source staging models (e.g., stg_yellow_tripdata.sql)
    ┗ 📁 core/               → Core dimensional and fact models (e.g., fact_trips.sql, dm_monthly_zone_revenue.sql)
📁 seeds/                     → Static reference data (e.g., taxi_zone_lookup.csv)
📁 snapshots/                 → (Empty for now – placeholder for future snapshots)
📁 tests/                     → (Empty for now – placeholder for future data tests)
📄 dbt_project.yml            → dbt project config file
📄 package-lock.yml           → Lists dbt packages used
```

---

## 🧠 Features Implemented
- 🏗️ **Staging Layer**: Normalized raw source data into structured models with tests and column-level documentation.
- 📊 **Core Layer**:
  - `fact_trips`: Stores cleaned fact data about taxi rides.
  - `dim_zones`: A dimension model listing NYC taxi zones.
  - `dm_monthly_zone_revenue`: Monthly revenue metrics per pickup zone.
- 🔁 **Macros**: Custom macros like `get_payment_type_description` for mapping codes to readable values.
- 📜 **Seed Data**: Taxi zone lookup table used in joins and relationship tests.
- 🔍 **Testing**: Applied dbt’s built-in schema and relationship tests to ensure data quality.
- 🧾 **Documentation**: Extensive column and model-level documentation via YAML.

---

## 🚀 Getting Started
### 1. Clone the Repository
```bash
git clone https://github.com/your-username/taxi_rides_ny.git
cd taxi_rides_ny
```

### 2. Install dbt & Dependencies
```bash
pip install dbt-core dbt-bigquery  # or any adapter of your choice
dbt deps
```

### 3. Configure Your Profile
Edit your `~/.dbt/profiles.yml` to point to your data warehouse (BigQuery, Snowflake, etc.).

### 4. Run the Project
```bash
dbt seed        # Load seed data
dbt run         # Run all models
dbt test        # Run tests defined in .yml files
dbt docs generate && dbt docs serve  # View interactive docs
```

---

## 📦 Dependencies
- [dbt-utils](https://hub.getdbt.com/dbt-labs/dbt_utils/latest/) – Reusable macros
- [codegen](https://hub.getdbt.com/dbt-labs/codegen/latest/) – Model and schema file generation

---

## 💡 Learnings
- Hands-on practice of the dbt workflow: `seed → staging → core → docs/tests`
- Understanding of dimensional modeling and analytical design
- Implementing reusable macros and YAML documentation

---

## 🛣️ Roadmap
- Add snapshots to track slowly changing dimensions
- Add more tests and assertions
- Expand macros to reduce redundancy
- Integrate with orchestration tools (Airflow/Kestra) or visualization tools (Looker Studio/Power BI)

---

## 🙌 Acknowledgements
Inspired by [DataTalksClub](https://github.com/DataTalksClub/data-engineering-zoomcamp). Thanks for the amazing open course!

---

Feel free to fork, clone, and expand this project. Contributions are welcome!

