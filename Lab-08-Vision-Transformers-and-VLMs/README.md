# Lab 03 – SVM Image Classification

## Problem Statement

The goal of this lab was to classify images as a cat, dog, or ship using a traditional machine-learning model.

I also compared two Support Vector Machine models to see whether the type of kernel affected the classification results.

## Approach

I loaded the CIFAR-10 dataset and selected only three classes:

- Cat
- Dog
- Ship

Before training the models, I prepared the images by:

- Converting them to grayscale
- Normalizing the pixel values
- Flattening each image into a one-dimensional feature vector

I trained two models:

- Linear Support Vector Machine
- RBF Support Vector Machine

The models were evaluated using accuracy and classification reports. I also displayed sample predictions to compare the predicted labels with the correct labels.

## Dataset

This lab used the CIFAR-10 dataset.

CIFAR-10 is a public image dataset containing small color images from 10 different classes. This lab used only the cat, dog, and ship classes.

The dataset was loaded directly through the notebook and was not uploaded to this repository.

It can be loaded with:

```python
from tensorflow.keras.datasets import cifar10

(x_train, y_train), (x_test, y_test) = cifar10.load_data()
```

Dataset source:

[CIFAR-10 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)

## Results

The Linear SVM achieved an accuracy of 54.7%.

The RBF SVM achieved an accuracy of 68.4%.

The RBF SVM performed better than the Linear SVM. This showed that the RBF kernel handled the image patterns better than the simpler linear decision boundary.

## Key Findings

This lab showed me that the choice of kernel can affect the performance of an SVM model.

The Linear SVM used a simpler decision boundary, while the RBF SVM could work with more complex patterns in the image data.

I also learned that converting images to grayscale and flattening them removes some color and spatial information. This can make image classification more difficult for traditional machine-learning models.

## Technologies and Dependencies

This lab used:

- Python
- NumPy
- Matplotlib
- TensorFlow
- Keras
- Scikit-learn
- Google Colab
- Jupyter Notebook

Important Scikit-learn tools included:

- `SVC`
- `accuracy_score`
- `classification_report`

## How to Run

1. Open `L03_Timory_Elham_ITAI1378.ipynb` in Google Colab or Jupyter Notebook.
2. Run the cells from top to bottom.
3. Allow the CIFAR-10 dataset to download automatically.
4. Run the preprocessing cells to select and prepare the images.
5. Train the Linear and RBF SVM models.
6. Review the accuracy results, classification reports, and sample predictions.


## Sample Results

### Cat Image Patch Grid

![Cat Image Patch Grid](./results/cat-vit-patch-grid.png)

This image shows how a Vision Transformer divides a cat image into 64 smaller patches. Each patch acts like a visual word that helps the model understand the complete image.

### Original Second Image

![Original Second Image](./results/second-image-original.png)

This was the second image used to compare different patch sizes.

### 48-Pixel Patch Grid

![48-Pixel Patch Grid](./results/second-image-48-pixel-patches.png)

The 48-pixel setting created 64 smaller patches. The smaller patches preserved more details from the image.

### 96-Pixel Patch Grid

![96-Pixel Patch Grid](./results/second-image-96-pixel-patches.png)

The 96-pixel setting created 16 larger patches. This required less processing but provided fewer visual details.

### Chart-Reading Test

![Chart Reading Test](./results/chart-reading-test.png)

The model was asked three questions about this sales chart. It answered two questions correctly but gave the wrong answer when calculating the difference between June and February.

## Additional Results

The `vlm-evaluation-results.txt` file contains the printed results from the image interview, alt-text test, chart-reading questions, hallucination test, and deployment audit.
