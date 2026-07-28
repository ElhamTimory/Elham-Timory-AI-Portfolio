# Lab 06 - Object Detection and Image Segmentation

## Overview
This lab focused on object detection and image segmentation. I used YOLO11 to detect and draw bounding boxes around them.
I also used YOLO11-seg to create masks around detected objects. SAM 2 was used with bounding boxes to create more detailed segmentation masks.

## Models Used
- YOLO11n for object detection
- YOLO11n-seg for instance segmentaion
- SAM 2 for foundation-model segmentation

## Images Used
The lab used sample images provided by Ultralytics, including a bus image and a soccer image.
The image were loaded through the notebook and are not included as a separate dataset in this repository.

## Results
YOLO11 detected a bus and four people in the sample bus image. ON the second image, it detected two people and a tie.
YOLO11-seg created six masks for the bus image. The masks showed the exact areas belonging to the bus, people, and other detected objects.
The confidence-threshold experiement showed that a lower threshold produces more detections, while a higher threshold keeps only predictions with stronger confidence. 
SAM 2 used the bounding boxes from YOLO11 as prompts and created detailed segmentation masks.
This lab did not train a new model, so there is no training or validation accuracy to report. 

## Technologies Used

- Python
- Ultralytics YOLO
- SAM 2
- OpenCV
- Pillow
- NumPy
- Matplotlib
- Google Colab
- Jupyter Notebook

## Skills Learned

- Object detection
- Bounding boxes
- Confidence scores
- Instance segmentation
- Segmentation masks
- Confidence thresholds
- Intersection over Union
- Precision and recall
- Mean Average Precision
- Detect-then-segment workflow


## Sample Results

### YOLO11 Object Detection

![YOLO11 Object Detection](./results/yolo11-object-detection.png)

This image shows the objects detected by YOLO11. The model placed bounding boxes around the bus and people and displayed a confidence score for each prediction.

### Confidence Threshold Comparison

![Confidence Threshold Comparison](./results/confidence-threshold-comparison.png)

This comparison shows how the confidence threshold changes the number of detections. Lower thresholds accept more predictions, while higher thresholds keep only stronger predictions.

### YOLO11 Instance Segmentation

![YOLO11 Instance Segmentation](./results/yolo11-instance-segmentation.png)

This result shows instance segmentation using YOLO11-seg. Each detected object has its own pixel-level mask.

### Detection and Segmentation Comparison

![Detection and Segmentation Comparison](./results/detection-vs-segmentation.png)

Object detection uses bounding boxes to show the location of objects. Segmentation gives a more detailed outline by identifying the pixels that belong to each object.

### YOLO11 and SAM 2

![YOLO11 and SAM 2](./results/sam2-detect-then-segment.png)

This image shows the detect-then-segment workflow. YOLO11 first found the objects, and SAM 2 used the bounding boxes to create segmentation masks.

### Intersection over Union

![Intersection over Union](./results/iou-overlap-examples.png)

This image shows different levels of overlap between the correct bounding box and the model’s predicted box. A higher IoU means the predicted box matches the correct box more closely.
