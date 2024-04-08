
# Dataproc

- fully managed
- highly scalable service
- used to run open-source tools and frameworks like Apache Spark, Apache Flink, Presto and + others.
- uses HDFS for storage (automatically installs Hadoop which allows parallel usage of Cloud Storage)

Used for:
- batch processing
- querying
- streaming
- machine learning

has in-built integration with other Google Cloud services for a complete data platform


### Dataproc connectors

| Connector                                   | Description                                                                                                                                                                                                                                                                                                   |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Cloud Storage](cloud-storage.md) connector | - default<br>- helps run Hadoop/Spark jobs directly on data in Cloud Storage <br>- Store data in Cloud Storage and access directly. <br>- You do not need to transfer it into HDFS first.                                                                                                                     |
| [BigQuery](bigquery) connector              | - enables programmatic read/write access to BigQuery<br>- ideal way to process data in BigQuery as <br>- command-line access not exposed<br>- helps run Hadoop/Spark jobs directly on data in Cloud Storage<br>- BigQuery Spark connector is used for Spark<br>- BigQuery Hadoop connector is used for Hadoop |
| BigQuery Spark connector                    | - Apache Spark SQL connector for Google BigQuery                                                                                                                                                                                                                                                              |
| [Cloud Bigtable](bigtable) with Dataproc    | - an excellent option for any Apache Spark/Hadoop uses that require Apache HBase<br>- Bigtable supports the Apache HBase APIs so it is easy to use Bigtable with Dataproc.                                                                                                                                    |
| [Pub/Sub Lite](pub-sub.md) Spark connector  | -  supports Pub/Sub Lite as an input source to Apache Spark Structured Streaming in the default micro-batch processing and experimental continuous processing modes.                                                                                                                                          |

All Cloud Dataproc clusters come with the BigQuery connector for Hadoop built in so that you can easily and quickly read and write BigQuery data to and from Cloud Dataproc.

