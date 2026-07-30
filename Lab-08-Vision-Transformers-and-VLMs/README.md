# Lab 08 – Vision Transformers and Vision-Language Models

## Problem Statement

The purpose of this lab was to understand how Vision Transformers and vision-language models process images.

The first part of the lab focused on image patches. The second part tested whether one vision-language model could complete several visual tasks by changing the written prompt.

## Approach

I first explored how a Vision Transformer divides an image into smaller square patches.

I compared two patch sizes:

- 48 × 48 pixels
- 96 × 96 pixels

I then used the SmolVLM-500M-Instruct model for several tasks, including:

- Identifying the main subject of an image
- Describing image details
- Classifying an image
- Counting objects
- Writing accessibility alt text
- Reading a chart
- Testing hallucinations
- Suggesting an action based on an image
- Reviewing whether the model would be suitable for workplace use

The same model was used for all these tasks. The task changed based on the prompt given to the model.

## Dataset and Images

This lab did not use a training dataset.

It used:

- A public cat image
- A second image uploaded in Google Colab
- A sales chart created inside the notebook

The public cat image came from the Hugging Face documentation-images dataset:

[Hugging Face Documentation Images](https://huggingface.co/datasets/huggingface/documentation-images)

The vision-language model used in this lab was:

[SmolVLM-500M-Instruct](https://huggingface.co/HuggingFaceTB/SmolVLM-500M-Instruct)

The public image and model were loaded directly through the notebook and were not uploaded separately to this repository.

## Results

### Image Patch Comparison

The image size used for the patch comparison was 384 × 384 pixels.

Using 48 × 48 pixel patches divided the image into 64 patches.

Using 96 × 96 pixel patches divided the image into 16 patches.

The smaller patch size preserved more visual detail, but it also created more patches for the model to process.

### Image Interview

The model correctly identified the main subject as a cat and described details from the image.

A simple prompt produced a shorter response. A more detailed prompt produced a more complete explanation.

### Classification and Counting

The model correctly classified the image as a cat and counted one main animal.

Some responses were more useful than others, showing that prompt wording affected the quality of the output.

### Chart-Reading Test

The model was asked three questions about a sales chart.

It correctly identified:

- June as the month with the highest sales
- 140 units as the sales value for March

It incorrectly calculated the difference between June and February.

The correct calculation was:

```text
210 - 95 = 115
```

The model answered 71 instead of 115.

### Hallucination Test

The model was asked questions about objects that were not visible in the images.

It correctly rejected several unsupported questions. However, when it was asked about a digital clock that was not present in the chart, it answered “Jun.”

This showed that the model could sometimes provide an answer even when the requested information was not available.

## Key Findings

This lab helped me understand that Vision Transformers process images as groups of patches.

Smaller patches preserve more image detail, while larger patches reduce the number of visual tokens the model must process.

I also learned that one vision-language model can complete several different tasks by changing the prompt.

Clear and specific prompts usually produced better answers. However, the model was not always reliable. It sometimes gave incorrect, incomplete, or unsupported responses.

Because of these limitations, the model’s answers should be reviewed by a person before they are used for important decisions.

## Technologies and Dependencies

This lab used:

- Python
- PyTorch
- Hugging Face Transformers
- SmolVLM-500M-Instruct
- Pillow
- Matplotlib
- Google Colab
- Jupyter Notebook

Important Hugging Face components included:

- `AutoProcessor`
- `AutoModelForImageTextToText`

A GPU is recommended for loading and running the vision-language model.

## How to Run

1. Open `L08_Elham_Timory_ITAI1378.ipynb` in Google Colab.
2. Change the runtime to GPU if one is available.
3. Run the installation and setup cells.
4. Run the image-patch examples.
5. Upload the second image when requested.
6. Load the SmolVLM-500M-Instruct model.
7. Run the image interview and visual tasks.
8. Run the chart-reading and hallucination tests.
9. Review the deployment audit at the end of the notebook.

An internet connection is required to download the public image and model files.

## Sample Results

### Cat Image Patch Grid

![Cat Image Patch Grid](./results/cat-vit-patch-grid.png)

This image shows how the cat image was divided into smaller patches.

### Original Second Image

![Original Second Image](./results/second-image-original.png)

This is the second image used for the patch-size comparison.

### 48-Pixel Patch Grid

![48-Pixel Patch Grid](./results/second-image-48-pixel-patches.png)

This version divided the image into 64 smaller patches.

### 96-Pixel Patch Grid

![96-Pixel Patch Grid](./results/second-image-96-pixel-patches.png)

This version divided the image into 16 larger patches.

### Chart-Reading Test

![Chart Reading Test](./results/chart-reading-test.png)

This chart was used to test whether the model could correctly read and calculate displayed values.

## Additional Results

The results folder also contains:

- `vlm-evaluation-results.txt` – Printed responses from the image interview, alt-text test, chart-reading test, hallucination test, decision preview, and deployment audit
