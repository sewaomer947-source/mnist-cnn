# MNIST Handwritten Digit Classifier (CNN)

A Convolutional Neural Network built with TensorFlow/Keras that classifies
handwritten digits (0-9) from the MNIST dataset. The model reaches
**99.04% accuracy on the test set**.

## What the notebook does
1. Loads the MNIST dataset (60,000 training and 10,000 test images, 28x28 grayscale)
2. Normalizes pixel values to [0, 1] and reshapes images to 28x28x1
3. Builds an 8-layer CNN
4. Trains for 5 epochs (batch size 32) with a 10% validation split
5. Evaluates accuracy on the test set
6. Plots training and validation accuracy per epoch
7. Shows 10 test digits with their actual and predicted labels
   (green title = correct, red title = wrong)

## Model architecture
| Layer | Type | Output shape | Params |
|-------|------|--------------|--------|
| 1 | Conv2D (32 filters, 3x3, ReLU) | (26, 26, 32) | 320 |
| 2 | MaxPooling2D (2x2) | (13, 13, 32) | 0 |
| 3 | Conv2D (64 filters, 3x3, ReLU) | (11, 11, 64) | 18,496 |
| 4 | MaxPooling2D (2x2) | (5, 5, 64) | 0 |
| 5 | Flatten | (1600) | 0 |
| 6 | Dense (128, ReLU) | (128) | 204,928 |
| 7 | Dropout (0.3) | (128) | 0 |
| 8 | Dense (10, Softmax) | (10) | 1,290 |

Total parameters: 225,034 (879.04 KB), all trainable.
Optimizer: Adam | Loss: sparse categorical crossentropy

## Results

| Epoch | Train accuracy | Train loss | Val accuracy | Val loss |
|-------|----------------|------------|--------------|----------|
| 1 | 94.66% | 0.1744 | 98.77% | 0.0453 |
| 2 | 98.02% | 0.0647 | 98.80% | 0.0422 |
| 3 | 98.49% | 0.0460 | 98.95% | 0.0373 |
| 4 | 98.86% | 0.0364 | 99.10% | 0.0348 |
| 5 | 99.11% | 0.0287 | 98.98% | 0.0370 |

**Final test accuracy: 99.04%**

Training and validation accuracy stay close together across all epochs,
so the model is not overfitting. Validation accuracy peaks at epoch 4
(99.10%) and dips slightly at epoch 5. All of the first 10 test digits
were predicted correctly.

## Files
- `CNN 8 layers.ipynb` - the CNN model described above
- `WITHOUT CNN.ipynb` - comparison model without convolutional layers
- `deep learning.ipynb` - deep learning practice notebook

## How to run
pip install tensorflow numpy matplotlib
Then open `CNN 8 layers.ipynb` in Jupyter or PyCharm and run all cells.