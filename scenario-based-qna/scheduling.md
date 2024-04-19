
Assume you have to setup a trigger for a real time prediction job. 
This can be done using following services:

1. [Cloud Scheduler](services/cloud-scheduler.md) can help setup a cron job schedule
2. Use [Vertex AI](services/vertex-ai.md) managed notebooks to execute and schedule training and prediction jobs
3. [Cloud Build](services/cloud-build.md) is a CI/CD offering on GCP. [Cloud Run](services/cloud-run.md) is a managed offering to deploy containers. You can use Cloud Build to deploy your application to Cloud Run
4. [Pub/Sub](services/pub-sub.md) and [Cloud Functions](services/cloud-function.md) can be used.
	- Cloud Functions directly listens to Cloud Storage triggers. Pub/Sub offers a more flexible approach where:
		1. Cloud Storage could publish a message (event) to a topic saying "New model uploaded."
		2. The Cloud Function would be subscribed to that specific topic.
		3. When Cloud Storage publishes the message, Pub/Sub delivers it to the Cloud Function, triggering the deployment process.
	- Setting this up is a challenge. So we can use [Cloud Workflows](services/cloud-workflows.md)

