
# Cloud Composer

- fully managed
- data workflow orchestration service
- you can author, schedule and monitor pipelines
- built on [Apache Airflow](apache-airflow.md)
- pipelines are configured as DAGs using python
- provides end-to-end integration with Google Cloud products
- better use this than airflow to avoid management and installation overhead
- best for batch workloads that can handle a few seconds of latency between tasks
