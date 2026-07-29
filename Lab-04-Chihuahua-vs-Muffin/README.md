# Lab 04 – Chihuahua vs. Muffin Neural Network

## Problem Statement

The purpose of this lab was to build a neural network that could classify an image as either a Chihuahua or a muffin.

These two classes can look surprisingly similar because both may contain similar colors, textures, shapes, and patterns.

The model needed to learn the visual differences between the two classes and make predictions on validation images.

## Approach

The images were resized to 224 by 224 pixels and converted into PyTorch tensors.

A traditional fully connected neural network was created using PyTorch. The image pixels were flattened into one long vector before being sent through the network.

The model included:

- An input layer with 150,528 pixel values
- A hidden layer with 128 features
- A hidden layer with 64 features
- A hidden layer with 32 features
- An output layer with two class scores

ReLU activation was used between the hidden layers.

The model was trained using:

- Cross-entropy loss
- SGD optimizer
- Learning rate of 0.01
- Batch size of 32
- 10 epochs

The model was evaluated on a separate validation set after each epoch.

## Dataset

This lab used the Chihuahua vs. Muffin image dataset from the workshop repository.

The notebook downloads the dataset by cloning the original GitHub repository.

Dataset source:

[Chihuahua vs. Muffin Workshop Dataset](https://github.com/patitimoner/workshop-chihuahua-vs-muffin)

The dataset contains separate folders for:

- Training images
- Validation images
- Chihuahua images
- Muffin images

The public dataset is not stored again in this portfolio repository.

## Results

The final training run achieved:

- Final training accuracy: 95.00%
- Final validation accuracy: 96.67%
- Final training loss: 0.2698
- Final validation loss: 0.3297

The validation accuracy improved during training and reached 96.67% during the final epoch.

The model correctly classified most validation images, although the task remained difficult because some muffins and Chihuahuas had similar textures and shapes.

## Key Findings

I learned that a basic neural network can classify images after the pixels are resized, normalized, and flattened.

However, flattening the image removes information about where features are located. The model sees the pixels as one long list rather than understanding nearby shapes and patterns.

I also learned that the optimizer, learning rate, batch size, and number of epochs can affect training performance.

This lab helped prepare for the next lab, where a convolutional neural network was used to preserve and learn spatial image features.

## Technologies and Dependencies

This lab used:

- Python
- PyTorch
- Torchvision
- Pillow
- Matplotlib
- tqdm
- Google Colab
- Jupyter Notebook

The main PyTorch components included:

- `torch.nn`
- `torch.optim`
- `CrossEntropyLoss`
- `DataLoader`
- Image transformations

## How to Run

1. Open `L04_Elham_Timory_ITAI1378.ipynb` in Google Colab.
2. Run the cells from top to bottom.
3. The notebook will clone the public dataset repository.
4. Allow the notebook to load and preprocess the images.
5. Run the training cell for all 10 epochs.
6. Review the training and validation results.
7. View the sample predictions at the end of the notebook.

A GPU can be used, but the notebook can also run on a CPU.

## Sample Results

### Sample Training Images

![Sample Training Images](./results/sample-training-images.png)

These are examples of Chihuahua and muffin images used during training.

### Validation Predictions

![Validation Predictions](./results/validation-predictions.png)

This result shows the model’s predictions for selected validation images.
