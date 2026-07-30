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

### Original CIFAR-10 Images

![Original Color Images](./results/original-color-images.png)

These are sample cat, dog, and ship images before preprocessing.

### Grayscale Images

![Grayscale Images](./results/grayscale-images.png)

These images show the selected CIFAR-10 classes after grayscale conversion.

### SVM Predictions

![SVM Sample Predictions](./results/svm-sample-predictions.png)

This result compares the predicted class with the correct class for several test images.

### Model Comparison

![SVM Model Comparison](./results/svm-model-comparison.png)

This chart compares the performance of the Linear SVM and RBF SVM models.
