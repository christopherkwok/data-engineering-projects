### Summary
git project to build a hybrid, end-to-end data pipeline that ingests raw public data, transform it through a structured lakehouse architecture, and serve analytics to end-users

| Platform | Role / Notes |
| --- | --- |
| [API / Public Dataset] | Source |
| Airflow DAG (Docker) | Orchestration layer |
| MinIO Bronze Bucket | Raw landing zone (local S3) |
| dbt + DuckDB | Transform: bronze → silver → gold |
| MinIO Gold Bucket | Parquet mart tables |
| Apache Superset | Dashboards (local) |
| GitHub Actions | Runs dbt tests on every push (cloud CI) |