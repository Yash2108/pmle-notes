# Vertex AI
#### ML problem types available in Google Cloud
![ml-problem-types](attachments/ml-problem-types.png)


#### User-managed vs Managed Notebook


| Managed notebook                                                                                                                                 | User-managed notebook                                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Automated shutdown for idle instances                                                                                                            | - Not supported out of the box.<br>- Can create a monitor to see when instances are idle using Cloud Monitoring and Cloud Functions and shut them down when not in use.                                                        |
| UI integration with Cloud Storage and BigQuery:<br>- Available from within JupyterLab’s navigation menu                                          | UI integration with Cloud Storage and BigQuery: <br>- There is no UI integration.<br>- Can use the BigQuery connector<br>- Can also use the BigQuery magic (\%%) command<br><br>For Cloud Storage<br>- Can use gsutil commands |
| Automated notebook runs                                                                                                                          | - This feature is not supported<br>- Can use Cloud Scheduler to schedule the training jobs or the notebook.                                                                                                                    |
| Custom containers: You can add your own custom container images to a managed notebook Jupyter instance.                                          | Custom containers: You have the choice to add custom containers.                                                                                                                                                               |
| Dataproc or Serverless Spark integration                                                                                                         | This feature is not supported.                                                                                                                                                                                                 |
| Frameworks: You can choose any framework supported once you have created a managed notebook.                                                     | Frameworks: You have the choice to create only one framework from all the supported frameworks                                                                                                                                 |
| Network and security: <br>- You can run this in the VPC in the same project. <br>- Shared VPC control is not yet supported for managed notebooks | Network and security: <br>- You can use VPC Service Controls to set up a user-managed notebooks instance within a service perimeter and implement other built-in networking and security features.                             |

## Vertex AI Vizier

- optimization service to tune hyperparameters
- Doesnt have a known objective function and is too costly to evaluate using one
- can optimize other tasks as well

Example use case:
- Optimize LR, Batch Size, etc
- Optimize usability of an application by testing different arrangements of UI elements
- Minimizing computing resources by identifying ideal buffer size and thread count
- Optimize amount of ingredients in a recipe to produce the most delicious version

The Vizier is an independent service. Hyperparameter tuning for custom training is a built-in feature that uses Vertex AI Vizier.