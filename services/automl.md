# AutoML

- A pretrained model should be tried first. Only if the pretrained model does not meet your requirements should you consider AutoML or custom models.
- Using pretrained model is serverless since only API calls are made.
- AutoML should be your choice if a pretrained model does not work for you and you do not have a team of ML engineers.


- When to use CPU vs GPU vs TPU:
	
	- CPUs
		- Rapid prototyping that needs flexibility
		- Models that train fast
		- Small models that work with small batch size
		- Custom TensorFlow operations written in C++
		- Limited by available I/O or the networking bandwidth of the host
		
	- GPUs
		- Models for which source code does not exist or is too tedious to change
		- Models with a significant number of custom TensorFlow operations so they need to run at least partially on a CPU
		- Models with TensorFlow ops that are not available on TPUs
		- Medium-to-large models with medium-sized batch
		
	- TPUs
		- Models that have a majority of matrix computations
		- Models that have no custom TensorFlow operations
		- Models that train for weeks or months
		- Large and very large models with very large effective batch sizes

	- Cloud TPUs are not suited to the following workloads:
    
	    - Programs that require frequent branching (if/else or conditional) or are dominated element-wise by algebra. TPUs are not designed to perform conditionals but they are designed for large-scale matrix multiplications.
	    
	    - Sparse data (data that has lot of zeros and only a small fraction of nonzero values), which leads to sparse memory access, is not suitable.
	    
	    - High precision is not well suited for TPUs. Do not expect double precision operations.
	    
	    - Deep neural networks that contain custom TensorFlow operations written in C++, especially if the custom operations in the main training loop are not suitable for TPUs.

## Deployment Phase

### Finding the Ideal Machine Type

Start by deploying a docker container to Compute Engine directly.

Benchmark the instance by calling prediction calls until the instance hits 90+ percent CPU utilization

Determine the queries per second (QPS) cost per hour of different machine types.

#### Example:

A custom container contains a Python web server process that can only effectively use 1 core and that process is calling a multithreaded ML model (such as most implementations of XGBoost), as QPS increases, the web server will start to “block”XGBoost because every XGBoost prediction will wait on the web server process.

If this deployed to a 2- or 4-core machine shape, the container will hit the QPS limits and the CPU utilization will be high, so the container is deployed to Vertex AI, and it will autoscale effectively.

## GPU Restrictions

- GPUs can only be used for a TensorFlow SavedModel or when you use a custom container that has been designed to take advantage of GPUs. You cannot use GPUs for scikit-learn or XGBoost models.
- GPUs are not available in some regions.
- You can use only one type of GPU DeployedModel resource or BatchPredictionJob, and there are limitations on the number of GPUs you can add depending on which machine type you are using.

TPUs are popularly used for training but usually are not used for serving in the cloud. However, edge TPUs are used for deploying models at the edge.