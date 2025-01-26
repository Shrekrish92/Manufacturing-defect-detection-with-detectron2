# Manufacturing Defect Detection with Detectron2  

## Overview  
This project focuses on identifying manufacturing defects on printed circuit boards (PCBs) using the Faster R-CNN object detection framework implemented with Detectron2. The workflow involves:  
1. **Dataset Format Conversion**: Converting PCB image data from YOLO format to COCO format.  
2. **Model Training and Evaluation**: Training a Faster R-CNN model with a ResNet-50 backbone and Feature Pyramid Network (FPN) on the converted dataset.  

## Dataset  
The dataset used for this project is **DeepPCB**, referenced from the [DeepPCB dataset paper](https://paperswithcode.com/dataset/deep-pcb).  

- The notebook `DeepPCB2COCO.ipynb` is used to convert the dataset to COCO format.  
- This process includes generating the JSON files required for COCO format compatibility.  

## Workflow  
1. **Dataset Preparation**:  
   - Convert YOLO format annotations to COCO format using `DeepPCB2COCO.ipynb`.  
   - Create training and validation image folders based on `trainval.txt` and `test.txt` files.  

2. **Model Training and Evaluation**:  
   - The training process is conducted using the Detectron2 model `faster_rcnn_R_50_FPN_3x`, which is pre-trained on the COCO dataset.  
   - The notebook `manufacturing_defect_detector.ipynb` handles:  
     - Dataset registration.  
     - Model configuration with pre-trained weights.  
     - Training the model.  
     - Evaluation of model performance.  

## Model Used  
This project utilizes the **Faster R-CNN** object detection framework with the following configuration:  
- **Faster R-CNN**:  
  - A two-stage object detection framework:  
    - **Stage 1**: Generates region proposals likely to contain objects using a Region Proposal Network (RPN).  
    - **Stage 2**: Refines the proposals and classifies them into specific object categories while performing bounding box regression.  
- **ResNet-50 Backbone**:  
  - A convolutional neural network with 50 layers for robust and hierarchical feature extraction.  
- **Feature Pyramid Network (FPN)**:  
  - Enhances detection performance by creating multi-scale feature representations, improving the detection of both large and small objects.  
- **COCO-Detection's faster_rcnn_R_50_FPN_3x**:  
  - A pre-trained model on the COCO dataset, leveraging 80 object categories.  
  - The "3x" indicates an extended training schedule for improved performance.  

## Installation and Setup  
1. Clone the repository:  
   ```bash  
   git clone https://github.com/your-username/manufacturing-defect-detection.git  
   cd manufacturing-defect-detection  
