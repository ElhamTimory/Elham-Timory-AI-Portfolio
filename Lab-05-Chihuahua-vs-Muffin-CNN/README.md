# Lab 05 - Chihuahua vs. Muffin CNN

## Overview
This lab used a Convolutional Neural Network to classify images as either a Chihuahua or a muffin. It built on the previous neural network lab by using convolutional layers that are better suited for image classification.
The model learned image features such as shapes, colors, edges, and textures. The dataset contained 120 training images and 30 validation images. 

## Model
The CNN was built with PyTorch. It included convolutional layers, ReLU activation functions, max-pooling layers, and fully connected layers. 
Cross-entropy loss was used to measure the model's error. The Adam Optimizer was used to update the model during training. 

## Dataset
The dataset contained two classses:
- Chihuahua
- Muffin

The training set contained 120 images, and the validation set contained 30 images. 
The dataset is loaded through the notebook and is not included in this repository. 

## Results
The model was trained for four epochs.
- **Best validation accuracy during training:** 100%
- **Final training accuracy:** 99.17%
- **Separate evaluation accuracy:** 83.33%
- **Classes:** Chihuahua and Muffin

The results show that the CNN performed well during training. However, the separate evaluation cell reported a lower accuracy, showing that model results can vary depending on how the model is evaluated. 

## Technologies Used
- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Pillow
- Google Colab
- Jupyter Notebook

## Skills Learned
- Convolutional Neural Networks
- Data augmentation
- Convolutional layers
- Max-pooling layers
- Cross-entropy loss
- Adam optimizer
- Model training and validation
- Prediction evaluation

## Sample Results

### CNN Validation Predictions

![CNN Validation Predictions](./results/cnn-validation-predictions.png)

This image shows the CNN’s predictions on the validation images. Green titles represent correct predictions, while red titles represent incorrect predictions.

The model correctly classified most of the validation images, but it confused some Chihuahuas and muffins because they can have similar colors, shapes, and textures.

## Additional Results

- `training-results.txt` contains the accuracy and loss values from each training epoch.
- `model-summary.txt` contains the structure of the CNN model.
