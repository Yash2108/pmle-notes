# Unit Testing for Machine Learning

Some tests that dont need trained parameters:
- Checking shape of model output
- Ensuring model output aligns with labels in dataset
- Checking the output ranges and ensuring it aligns with your expectations (e.g., the output of a classification model should be a distribution with class probabilities that sum to 1). 
- Making sure a single gradient step on a batch of data yields a decrease in your loss. 
- Making assertions about your datasets.
- Checking for label leakage between your training and validation datasets.

# Testing for Algorithmic Correctness

1. Train your model for a few iterations and verify that the loss decreases. 
2. Train your algorithm without regularization. If your model is complex enough, it will memorize the training data and your training loss will be close to 0. 
3. Test specific subcomputations of your algorithm. For example, you can test that a part of CNN runs once per element of the input data.

