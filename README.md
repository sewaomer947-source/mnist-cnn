# MNIST Handwritten Digit Recognition with a CNN

A convolutional neural network built with TensorFlow/Keras to classify
handwritten digits from the MNIST dataset.

## Model
8 layers: 2 convolution layers (32 and 64 filters), 2 max-pooling layers,
a flatten layer, a dense layer (128 units), dropout (0.3), and a
10-class softmax output. 225,034 parameters.

## Training
- Adam optimizer, sparse categorical cross-entropy
- 5 epochs, batch size 32, 10% of the training data held out for validation

## Results
- Final training accuracy: 99.08%
- Final validation accuracy: 98.93%
- **Test accuracy: 98.99%**
- All 10 sample test digits were predicted correctly.

## Notes
- MNIST is a clean, simple benchmark. A high score here does not mean the
  model works on real-world images. See my CIFAR-10 project, where the
  same kind of model scored lower and struggled on real photos.
