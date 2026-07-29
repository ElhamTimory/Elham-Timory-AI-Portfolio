# Lab 06 – Object Detection and Image Segmentation

## Problem Statement

The purpose of this lab was to understand the differences between image classification, object detection, and image segmentation.

Instead of predicting only one label for an entire image, the models needed to locate individual objects and identify the pixels belonging to each object.

The lab also compared a specialist model, YOLO11, with a foundation segmentation model, SAM 2.

## Approach

YOLO11 was used for object detection.

The model placed bounding boxes around detected objects and provided:

- Class labels
- Confidence scores
- Bounding-box coordinates

Different confidence thresholds were tested to observe how the threshold affected the number of detections.

YOLO11-seg was then used for instance segmentation. It produced a separate pixel-level mask for each detected object.

SAM 2 was also tested using bounding boxes as prompts. This created a detect-then-segment workflow:

1. YOLO11 detected and labeled the objects.
2. SAM 2 used the bounding boxes to create detailed masks.

The lab also included examples explaining Intersection over Union, precision, recall, and mean Average Precision.

## Dataset

This lab did not train a new model or use a separate training dataset.

It used sample images provided by Ultralytics, including:

- `bus.jpg`
- `zidane.jpg`

The images were downloaded automatically through the notebook.

Image and model source:

[Ultralytics](https://ultralytics.com/)

The models used were pretrained:

- YOLO11n
- YOLO11n-seg
- SAM 2.1 Small

The model weight files and public sample images were not uploaded separately to this repository.

## Results

On the bus image, YOLO11 detected:

- Four people
- One bus
- One stop sign

YOLO11-seg produced six object masks for the bus image.

On the Zidane image, YOLO11-seg detected:

- Two people
- One tie

It produced three segmentation masks.

The confidence-threshold comparison showed that:

- Lower thresholds accepted more detections
- Higher thresholds removed weaker detections
- Very high thresholds could miss valid objects

SAM 2 created detailed masks after receiving YOLO bounding boxes as prompts.

This lab used pretrained models and did not train a new model. Therefore, it did not produce training accuracy, validation loss, or training curves.

## Key Findings

I learned that image classification predicts a label for the entire image, while object detection locates objects with bounding boxes.

Instance segmentation gives more detail by identifying the pixels belonging to each object.

YOLO is useful when the model needs to find objects and name their classes. SAM 2 can segment almost any object when it receives a prompt, but it does not automatically provide the object’s class name.

I also learned that confidence thresholds involve a tradeoff. A lower threshold may detect more objects but can increase false positives. A higher threshold may reduce false positives but can miss real objects.

## Technologies and Dependencies

This lab used:

- Python
- Ultralytics
- YOLO11
- YOLO11-seg
- SAM 2
- NumPy
- Pillow
- Matplotlib
- Google Colab
- Jupyter Notebook

The main installation is:

```python
pip install ultralytics

## Sample Results

### YOLO11 Object Detection

![YOLO11 Object Detection](./results/yolo11-object-detection.png)

This result shows bounding boxes, object labels, and confidence scores produced by YOLO11.

### Confidence Threshold Comparison

![Confidence Threshold Comparison](./results/confidence-threshold-comparison.png)

This comparison shows how changing the confidence threshold affects the number of accepted detections.

### YOLO11 Instance Segmentation

![YOLO11 Instance Segmentation](./results/yolo11-instance-segmentation.png)

This image shows separate pixel-level masks for the detected objects.

### Detection and Segmentation Comparison

![Detection and Segmentation Comparison](./results/detection-vs-segmentation.png)

This comparison shows the difference between bounding-box detection and pixel-level segmentation.

### YOLO11 and SAM 2

![YOLO11 and SAM 2](./results/sam2-detect-then-segment.png)

This result shows the detect-then-segment workflow. YOLO11 first located the objects, and SAM 2 created detailed masks.

### Intersection over Union

![IoU Overlap Examples](./results/iou-overlap-examples.png)

This image shows how different levels of overlap affect the Intersection over Union score.

## Additional Result Files

- `detection-summary.txt` – Printed detection information from the notebook
