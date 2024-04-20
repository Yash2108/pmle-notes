# Multi-service Notes

#### ML workflow to GCP services mapping
![ml-workflow-to-service-mapping](attachments/ml-workflow-to-service-mapping.png)


#### [BigQuery](bigquery.md) vs [AutoML](AutoML) vs [VertexAI](vertex.md) custom Model
![bigquery-vs-autoML-vs-vertexai](attachments/bigquery-vs-autoML-vs-vertexai.png)

#### [Memorystore](memorystore.md) vs [Datastore](datastore.md) vs [Bigtable](bigtable.md)
![memorystore-vs-datastore-vs-bigtable](attachments/memorystore-vs-datastore-vs-bigtable.png)

#### Storage guidance

| Type of Data                               | Product                                                    |
| ------------------------------------------ | ---------------------------------------------------------- |
| Tabular data                               | [BigQuery](bigquery.md), BigQuery ML                       |
| Image, video, audio, and unstructured data | [Google Cloud Storage](cloud-storage.md)                   |
| Unstructured data                          | [Vertex Data Labeling](vertex.md#Vertex%20Data%Labeling)   |
| Structured data                            | [Vertex Al Feature Store](vertex.md#Feature%20Store)       |
| For AutoML image, video, text              | [Vertex Al Managed Datasets](vertex.md#Managed%20Datasets) |


If using TensorFlow:
- store data as sharded TFRecord files. 
- can also use TF I/O to manage data in Parquet format for training. 

Else:
- store as Avro files in [Google Cloud Storage](cloud-storage.md)

#### [Kubeflow Pipelines](kubeflow.md#Kubeflow%20Pipelines) vs. [Vertex AI Pipelines](vertex.md#Vertex%20AI%20Pipelines) vs. [Cloud Composer](cloud-composer.md)

|                                       | Kubeflow Pipelines                                                                                                                                                    | Vertex AI Pipelines                                                                                                                 | Cloud Composer                                                                                                                                                                                |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Management and support for frameworks | Used to orchestrate ML workflows in any supported framework such as TensorFlow, PyTorch, or MXNet using Kubernetes. <br><br>Can be set up onpremises or in any cloud. | Managed serverless pipeline to orchestrate either Kubeflow Pipelines or TFX Pipeline. <br><br>No need to manage the infrastructure. | Managed way to orchestrate ETL/ ELT pipelines using Apache Airflow. It’s a Python-based implementation. <br><br>You would use a workflow to solve complex data processing workflows in MLOps. |
| Failure handling                      | You would need to handle failures on metrics as this is not supported out of the box.                                                                                 | Since Vertex AI pipelines runs the Kubeflow Pipelines, you can use the Kubeflow failure management on metrics.                      | Failure management for built-in GCP metrics to take action on failure or success.                                                                                                             |

## Hybrid or Multicloud Strategies

- GCP AI APIs can be integrated anywhere on-premises or in any application. You can call the pretrained APIs using an AWS Lambda function and take advantage of GCP ML
- BigQuery Omni lets you run BigQuery analytics on data stored in Amazon S3 or Azure Blob Storage. If you want to join the data present in AWS or Azure with the data present in Google Cloud regions or if you want to utilize BigQuery ML capabilities, use the LOAD DATA SQL statement. This SQL statement lets you transfer data from BigQuery Omni–accessible S3 buckets into BigQuery native tables.
- To train custom ML models on Vertex AI, Vertex AI is integrated with BigQuery and you can access the data from BigQuery Omni (data in S3, Azure) to train an AutoML or custom ML model using Vertex AI Training. You can also use BigQuery ML on the data.