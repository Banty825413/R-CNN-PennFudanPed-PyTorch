# R-CNN-PennFudanPed-PyTorch
Pedestrian Detection using Faster R-CNN (PyTorch)
Project Overview

This project implements a Pedestrian Detection system using Faster R-CNN with a ResNet-50 and Feature Pyramid Network (FPN) backbone, built using PyTorch and Torchvision.

The objective is to detect pedestrians in images and identify their locations using bounding boxes and confidence scores.

The model uses transfer learning with pretrained COCO weights. Its classification head is customized for pedestrian detection, with two classes: background and person.

The dataset contains three main directories:

PennFudanPed/

├── PNGImages/       # Original pedestrian images
├── PedMasks/        # Instance segmentation masks
└── Annotation/      # Image annotations

Technologies Used

Python

PyTorch

Torchvision

Faster R-CNN

ResNet-50

Feature Pyramid Network (FPN)

NumPy

Matplotlib

Implementation

The project covers the following steps:

Custom Dataset Preparation: Created a custom PyTorch Dataset class to load images and their corresponding annotations.

Data Preprocessing: Converted images into tensors, scaled pixel values, and prepared bounding-box coordinates and class labels.

Data Splitting: Divided the dataset into training and testing subsets.

Model Configuration: Loaded a pretrained Faster R-CNN ResNet-50 FPN model and replaced its classification head for pedestrian detection.

Model Training: Trained the model using multiple loss components:

Classification Loss

Bounding Box Regression Loss

RPN Objectness Loss

RPN Bounding Box Regression Loss

Evaluation: Evaluated detection performance using Mean Average Precision (mAP) and IoU-based metrics.

Prediction and Visualization: Generated pedestrian predictions, filtered detections using confidence thresholds, and visualized bounding boxes with confidence scores.

Output Saving: Saved the predicted images with bounding-box annotations to an external folder.

Model Evaluation

The model achieved the following evaluation results:

Metric

Score

mAP

0.8046

mAP@0.5

0.9905

These results indicate strong pedestrian detection performance on the evaluated test dataset.

Prediction

The trained model generates:

Predicted pedestrian bounding boxes.

Class labels.

Confidence scores.

Predictions are visualized using Torchvision's draw_bounding_boxes() and Matplotlib.
