# Multi-service Notes

#### ML workflow to GCP services mapping
![ml-workflow-to-service-mapping](attachments/ml-workflow-to-service-mapping.png)


#### [BigQuery](bigquery.md) vs [AutoML](AutoML) vs [VertexAI](services/vertex-ai) custom Model
![bigquery-vs-autoML-vs-vertexai](attachments/bigquery-vs-autoML-vs-vertexai.png)

#### [Memorystore](memorystore.md) vs [Datastore](datastore.md) vs [Bigtable](bigtable.md)
![memorystore-vs-datastore-vs-bigtable](attachments/memorystore-vs-datastore-vs-bigtable.png)

#### Storage guidance
![storage-guidance](attachments/storage-guidance.png)

If using TensorFlow:
- store data as sharded TFRecord files. 
- can also use TF I/O to manage data in Parquet format for training. 

Else:
- store as Avro files in [Google Cloud Storage](cloud-storage.md)

