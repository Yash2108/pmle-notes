# Vertex [Explainable AI](ml-topics/explainable-ai)

The following services are supported:
- AutoML image models (classification only)
- AutoML tabular models (classification and regression only)
- Custom TF models on image data
- Custom TF models on tabular data

### Feature Attribution

is done using three methods:
1. Sampled Shapley
2. Integrated Gradients
	1. provides local feature importance
	2. doesnt provide global feature importance
	3. doesnt explain feature interactions and combinations
4. XRAI (eXplanation with Ranked Area Integrals)

![explanable-ai-methods](attachments/explanable-ai-methods.png)

#### Differentiable Models
All operations in the model are differentiable. Ex: Neural Networks
Preferred Method: Integrated Gradients
#### Non-Differentiable Models
The models that include non-differentiable operations like rounding or decoding.
Example: An ensemble of Neural Network and Decision Tree.
Preferred Method: Sampled Shapley


### Explanations available after configuration

- Online Explanations
	- Synchronous requests to the Vertex AI API. Similar to online predictions
	- Returns predictions with feature attribution
- Batch Explanations
	- Asynchronous requests. 
- Local Kernel Explanations
	- For custom trained models. 
