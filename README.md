MNIST Handwritten Digit Recognition with a CNN

A convolutional neural network built with TensorFlow/Keras to classify handwritten digits (28x28 grayscale images) from the MNIST dataset. The code is in mnist_cnn.ipynb.

Model

8 layers: 2 convolution layers (32 and 64 filters), 2 max-pooling layers, a flatten layer, a dense layer (128 units), a dropout layer (0.3), and a 10-class softmax output. 225,034 trainable parameters.

Training
Adam optimizer, sparse categorical cross-entropy loss
5 epochs, batch size 32, 10% of the training data held out for validation
Results
Final training accuracy: 99.08%
Final validation accuracy: 98.93%
Test accuracy: 98.99%
The first 10 test digits were all predicted correctly.
The notebook also plots training and validation accuracy per epoch.
Notes
MNIST is a clean, simple benchmark. A high score here does not mean a model works on real-world images.
For comparison, see my CIFAR-10 project in this repository. A similar model reached 69.3% on the CIFAR-10 test set and identified 6 of 12 real photos correctly.
