# Augmentation

Increases size of dataset using transformation techniques

Can be done in 2 ways:
1. Offline Augmentation
2. Online Augmentation

## Offline Augmentation

- Perform all transformation on the entire dataset before training

- Only do this when you have a small dataset

## Online Augmentation

- AKA *augmentation on-the-fly*
- Perform augmentation on mini-batches right before feeding into the model
- Usually used with large datasets

## Augmentation Techniques

- Flip 
- Rotate
- Crop
- Scale
- Gaussian noise (adding just the right amount of noise to enhance the learning capability)
- Translate 
- Conditional generative adversarial networks (GANs) to transform an image from one domain to an image in another domain 
- Transfer learning to give the models a better chance with the scarce amount of data