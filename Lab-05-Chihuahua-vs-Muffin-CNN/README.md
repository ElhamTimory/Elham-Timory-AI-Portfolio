# Lab 05 – Chihuahua vs. Muffin CNN

## Problem Statement

The purpose of this lab was to improve the Chihuahua vs. Muffin classifier by using a convolutional neural network.

The traditional neural network from Lab 04 flattened the images before training. This removed information about the location of visual features.

The CNN was designed to learn important image features such as edges, shapes, textures, and patterns while preserving spatial information.

## Approach

The images were resized and converted into PyTorch tensors.

A convolutional neural network was created with three convolutional sections.

Each section contained:

- A convolutional layer
- ReLU activation
- Max-pooling

The convolutional layers used:

- 32 filters
- 64 filters
- 128 filters

After feature extraction, the output was flattened and passed through:

- A fully connected layer with 512 units
- ReLU activation
- Dropout with a rate of 0.5
- A final output layer with two class scores

The model was trained using:

- Cross-entropy loss
- Adam optimizer
- Learning rate of 0.001
- Batch size of 16
- Four epochs

## Dataset

This lab used the Chihuahua vs. Muffin image dataset.

Dataset source:

[Chihuahua vs. Muffin Workshop Dataset](https://github.com/patitimoner/workshop-chihuahua-vs-muffin)

The notebook used:

- 120 training images
  - 65 Chihuahua images
  - 55 muffin images
- 30 validation images
  - 17 Chihuahua images
  - 13 muffin images

The dataset is public and was downloaded through the notebook. It was not uploaded separately to this repository.

## Results

The validation accuracy during training was:

- Epoch 1: 96.67%
- Epoch 2: 96.67%
- Epoch 3: 93.33%
- Epoch 4: 100.00%

The best validation result during training was:

- Best validation accuracy: 100.00%
- Best epoch: Epoch 4
- Epoch 4 validation loss: 0.0409
- Epoch 4 training accuracy: 99.17%

A separate evaluation cell later reported:

- Validation accuracy: 83.33%

This difference may have resulted from the evaluation being run after a different model state, random image transformations, or a separate execution of the notebook.

Both results are included because they were produced by the notebook.

## Key Findings

I learned that convolutional layers can automatically learn visual features from images.

Pooling layers reduce the feature-map size while keeping important information. Dropout helps reduce overfitting by randomly turning off some neurons during training.

The CNN achieved strong validation results, but the small dataset made the evaluation less stable. A difference of only a few images could significantly change the final accuracy.

I also learned that notebook cells should be run in order so that the final evaluation uses the same trained model state.

## Technologies and Dependencies

This lab used:

- Python
- NumPy
- PyTorch
- Torchvision
- Pillow
- Matplotlib
- tqdm
- torchsummary
- Google Colab
- Jupyter Notebook

Main model components:

- `Conv2d`
- `ReLU`
- `MaxPool2d`
- `Dropout`
- `Linear`
- `CrossEntropyLoss`
- Adam optimizer

## How to Run

1. Open `L05_Timory_Elham_ITAI1378.ipynb` in Google Colab.
2. Run all cells from top to bottom.
3. Allow the notebook to download and organize the image dataset.

A GPU is recommended but is not required for this small dataset.

## Sample Results

### CNN Validation Predictions

![CNN Validation Predictions](./results/cnn-validation-predictions.png)

This image shows validation examples with their predicted and correct labels.

## Additional Result Files

The results folder also contains:

- `training-results.txt` – Printed training loss and accuracy for each epoch
- `model-summary.txt` – The CNN architecture and parameter summary
