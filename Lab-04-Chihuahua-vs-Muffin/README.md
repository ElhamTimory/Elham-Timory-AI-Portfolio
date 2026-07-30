# Lab 04 – Chihuahua vs. Muffin Neural Network

## Problem Statement

The purpose of this lab was to build a neural network that could classify an image as either a Chihuahua or a muffin.

This is a challenging image-classification problem because some Chihuahuas and muffins can have similar colors, textures, and shapes.

## Approach

The images were resized to 224 by 224 pixels and converted into PyTorch tensors.

Before the images entered the neural network, their pixels were flattened into one long numerical vector.

The network included:

- An input layer
- Three hidden layers
- ReLU activation functions
- An output layer with two class scores

The model was trained using cross-entropy loss and the SGD optimizer.

The training settings included:

- Learning rate: 0.01
- Batch size: 32
- Number of epochs: 10

The model was evaluated on the validation set after each epoch.

## Dataset

This lab used the Chihuahua vs. Muffin image dataset from a public workshop repository.

Dataset source:

[Chihuahua vs. Muffin Workshop Dataset](https://github.com/patitimoner/workshop-chihuahua-vs-muffin)

The notebook downloaded the data by cloning the original repository.

The dataset contains separate folders for:

- Chihuahua training images
- Muffin training images
- Chihuahua validation images
- Muffin validation images

The dataset was not uploaded again to this portfolio repository.

## Results

In the final saved run, the model reached approximately:

- Training accuracy: 93.33%
- Validation accuracy: 96.67%
- Training loss: 0.2531
- Validation loss: 0.3092

The model correctly classified most of the validation images.

However, some images remained difficult because certain muffins and Chihuahuas had similar visual features.

## Key Findings

This lab helped me understand how a basic neural network can be used for image classification.

I learned that images must be resized, normalized, and converted into numerical values before entering the model.

I also learned that flattening an image removes information about where features are located. The network sees one long list of pixels instead of understanding nearby shapes and patterns.

This limitation prepared me for the next lab, where I used a convolutional neural network.

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

Important components included:

- `torch.nn`
- `torch.optim`
- `CrossEntropyLoss`
- `DataLoader`
- Image transformations

## How to Run

1. Open `L04_Elham_Timory_ITAI1378.ipynb` in Google Colab.
2. Run the cells from top to bottom.
3. Allow the notebook to download the image dataset.
4. Run the model-training cell.
5. Review the training and validation results.
6. View the sample predictions at the end of the notebook.

The notebook can run on a CPU, although a GPU may make training faster.

## Sample Results

### Sample Training Images

![Sample Training Images](./results/sample-training-images.png)

These are examples of Chihuahua and muffin images used during training.

### Validation Predictions

![Validation Predictions](./results/validation-predictions.png)

This result shows validation images with their predicted and correct labels.
