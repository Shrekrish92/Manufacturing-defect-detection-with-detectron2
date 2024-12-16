# Manufacturing-defect-detection-with-detectron2
This is a project that converts PCB image data that is in YOLO format to COCO format. Then uses faster RCNN from detectron2 to identify manufacturing defects.

## Dataset used:
This is the link to the paper referred to convert the data set format to COCO and the dataset used. 
https://paperswithcode.com/dataset/deep-pcb

## Overview
The notebbook DeepPCB2COCO.ipynb converts the dataset to COCO. This notebook makes the json files required fo rthe COCO format. Later before strating the training make the train and val image folders using the trainval.txt and test.txt files. The training is done using the COCO-Detection's faster_rcnn_R_50_FPN_3x model. The notebook manufacturing_defect_detector.ipynb starts with creating the folders and then registering the dataset on detectron2. Then model is configured and trained with pretrained weights and later evaluated.

## Model used
Model refers to a specific configuration of the Faster R-CNN object detection framework implemented with a ResNet-50 backbone and Feature Pyramid Network (FPN). It is trained on the COCO dataset, a large-scale object detection dataset containing 80 object categories. The "3x" indicates the training schedule used, typically implying more iterations for better performance.
1. Faster R-CNN:
A popular two-stage object detection framework.
Stage 1: Generates region proposals likely to contain objects (using a Region Proposal Network or RPN).
Stage 2: Refines these proposals and classifies them into specific object categories, along with bounding box regression.
2. ResNet-50 Backbone:
ResNet-50 is a convolutional neural network with 50 layers, known for its efficiency and robustness in extracting hierarchical image features.
It provides the base feature extraction for the Faster R-CNN pipeline.
3. Feature Pyramid Network (FPN):
Enhances detection performance by leveraging a multi-scale feature representation.
Helps detect both large and small objects effectively by creating a pyramid of features at different scales.

