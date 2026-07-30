# Lab 02 – Digital Image Processing

## Problem Statement

This lab was about understanding how computers store and process digital images. An image may look simple to us, but a computer sees it as a group of numerical pixel values.

In this lab, I explored how changing those pixel values affects the way an image looks. I worked with grayscale conversion, brightness, contrast, filters, and edge detection.

## Approach

I started by loading a color image and looking at how its red, green, and blue values were represented.

I then applied several image processing techniques:

- Converted the original image to grayscale
- Increased and decreased brightness
- Adjusted the contrast
- Applied blur and sharpening filters
- Used edge detection
- Compared the original image with the processed images

The results were displayed using Matplotlib so the effects of each operation could be seen clearly.

## Dataset

This lab did not use a large dataset. It used sample images for testing different image-processing operations.

The images were loaded and processed directly inside the notebook. No public dataset was uploaded to this repository.

## Results

The grayscale conversion removed the color information while keeping the main shapes and brightness levels in the image.

Increasing the pixel values made the image brighter, while decreasing them made the image darker. Adjusting contrast changed the difference between the lighter and darker parts of the image.

The blur filter reduced small details, while the sharpening filter made some edges and features more noticeable. Edge detection highlighted areas where the pixel values changed quickly.

This lab did not train a machine-learning model, so there were no accuracy or loss scores.

## Key Findings

This lab helped me understand that image-processing effects are created by changing pixel values in specific ways.

I also learned that filters are useful for preparing images before they are used in a computer-vision model. For example, edge detection can highlight important shapes, while blur can reduce noise.

## Technologies and Dependencies

This lab used:

- Python
- NumPy
- Pillow
- OpenCV
- Matplotlib
- Google Colab
- Jupyter Notebook

## How to Run

1. Open the `.ipynb` notebook in Google Colab or Jupyter Notebook.
2. Run the cells from top to bottom.
3. Make sure the required image is available to the notebook.
4. View the processed images in the output cells.

## Sample Results

### Original RGB Image

![Original RGB Image](./results/rgb-color-image.png)

This is the original color image before any processing was applied.

### Grayscale Conversion

![Grayscale Conversion](./results/grayscale-conversion.png)

This result shows the image after the color information was removed.


### Filters and Edge Detection

![Filters and Edge Detection](./results/filters-edge-detection.png)

This image shows the results of blur, sharpening, and edge-detection filters.

### Image-Processing Effects

![Image-Processing Effects](./results/image-processing-effects.png)

This comparison summarizes several of the image-processing operations completed in the lab.
