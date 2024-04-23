
# BigQuery

data warehouse product
fully managed
serverless


#### Tools to read BigQuery data
![tools-to-read-bigquery-data](attachments/tools-to-read-bigquery-data.png)

## BigQuery ML

#### Explainability

| Model Type                            | Explainability Method                        | Description                                                                                                     |
| ------------------------------------- | -------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Linear and logistic regression        | Shapley values and standard errors, p-values | This is the average of all the marginal contributions to all possible coalitions.                               |
| Boosted Trees                         | Tree SHAP, Gini-based feature importance     | Shapley values optimized for decision tree–based models.                                                        |
| Deep Neural Network and Wide-and-Deep | Integrated gradients                         | A gradients-based method to efficiently compute feature attributions with same axiomatic properties as Shapley. |
| Arima_PLUS                            | Time-series decomposition                    | Decompose into multiple components if present in the time series                                                |


## BigQuery Data Transfer Service

use this service to transfer data from following sources:

- Data warehouses (teradata, amazon redshift)
- External cloud provider amazon s3
- Google SaaS apps like [Cloud Storage](cloud-storage.md), Google Ads, etc

after a one-time config, automatically loads data on a regular basis