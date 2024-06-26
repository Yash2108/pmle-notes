# Machine Learning Models

## Artificial Neural Networks (ANN)
Simple network with 1 input, 1 hidden and 1 output layer.

![artificial-neural-networks](attachments/artificial-neural-networks.png)

## Deep Neural Networks (DNN)

ANN with more hidden layers

![deep-neural-networks](attachments/deep-neural-networks.png)

## Convolutional Neural Networks (CNN)

DNNs but for images

## Recurrent Neural Networks (RNN)

Designed to be used on sequences of data

Use cases:
- NLP where text is fed in a sequence
- Time-series forecasting
- Speech recognition

## Long-Short Term Memory Networks (LSTM)

A popular type of RNN.

Similar use cases as RNN with better success.

LSTMs can be used in a model to accept a sequence of input data and make a prediction, such as to assign a class label or predict a numerical value like the next value or values in the sequence

# Loss Functions

![loss-functions](attachments/loss-functions.png)

Use sparse categorical cross-entropy when your classes are mutually exclusive (when each sample belongs exactly to one class) 

Use categorical cross-entropy when one sample can have multiple classes or labels

# Hyperparameter Tuning

## Batch Size

The following are the best practices for tuning batch size: 

- Using a smaller batch size lets your gradient update more often per epoch, which can result in a larger decrease in loss per epoch. Furthermore, models trained using smaller batches generalize better.
- Large batch size can lead to out of memory error while training neural networks.

## Learning Rate

- Both low and high learning rates result in wasted time and resources. 
- A lower learning rate means more training time. 
- More time results in increased cloud GPU costs. 
- A higher rate could result in a model that might not be able to predict anything accurately. 
- If the learning rate is too small, training will take ages; if it’s too large, training will bounce around and ultimately diverge.




