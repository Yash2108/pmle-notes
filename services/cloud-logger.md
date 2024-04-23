# Cloud Logger

3 kinds of logs:
1. Container Logging
	- logs *stdout* and *stderr* from prediction nodes
2. Access Logging
	- logs timestamps, latency for each request to Cloud Logging
	- enabled by default
3. Request-Response Logging
	- logs a sample of online prediction requests and responses to [BigQuery](services/bigquery.md) table

### Restriction
- If Model Monitoring is enabled, Request-Response Logging cannot be enabled
- If Request-Response Logging is enabled and Model Monitoring is enabled later, Request-Response Logging cannot be modified.

