# Brain Tumor Detection and Segmentation using Deep Learning

This project focuses on the detection and segmentation of brain tumors from MRI scans using deep learning techniques. It explores both classification and segmentation tasks, leveraging convolutional neural networks (CNNs) and transfer learning with pre-trained models.

# Project Overview
The goal of this project is to build robust models that can:

Classify MRI images as containing a brain tumor or being healthy.
Segment the exact region of a tumor within an MRI image.
Dataset
The project utilizes the LGG MRI Segmentation dataset from Kaggle, which includes MRI scans and corresponding tumor masks. The dataset consists of a collection of brain MRI images, with masks indicating the presence and location of low-grade glioma (LGG) tumors.

# Methodology
1. Data Preparation
Image and Mask Loading: Custom functions are used to load and preprocess MRI images and their corresponding masks, including resizing and normalization.
Labeling for Classification: Images are labeled as 'healthy' (0) or 'tumor' (1) based on the presence of a tumor mask.
Data Splitting: The dataset is split into training, validation, and test sets to ensure robust model evaluation.
2. Classification Task
Model 1: Custom CNN
A custom Convolutional Neural Network (CNN) architecture is designed and trained from scratch for binary classification (tumor/healthy).

Architecture: Multiple convolutional layers, batch normalization, max pooling, and fully connected layers.
Training: Adam optimizer and Cross-Entropy Loss are used.
Results: Achieved an accuracy of approximately 77.23%.
Model 2: Transfer Learning with ResNet50
To improve performance, transfer learning is applied using a pre-trained ResNet50 model (ImageNet weights).

Approach: The pre-trained ResNet50 layers are frozen, and a custom classification head is added and trained.
Training: Adam optimizer and Cross-Entropy Loss are used.
Results: Significantly improved accuracy to approximately 81.93%.
Interpretability with Grad-CAM
Grad-CAM (Gradient-weighted Class Activation Mapping) is used to visualize the regions of interest that the classification model focuses on when making predictions. This helps in understanding which parts of the MRI scan contribute most to the tumor/healthy classification.

3. Segmentation Task
Model: UNet Architecture
For precise tumor localization, a UNet model is implemented.

# Architecture:
The UNet consists of an encoder (using a pre-trained ResNet18) and a custom decoder for upsampling and mask prediction.
Loss Function: Focal Tversky Loss is employed, which is particularly effective for medical image segmentation tasks with class imbalance.
Training: Adam optimizer is used.
Evaluation Metrics: Intersection over Union (IoU) and Dice Coefficient are used to quantify segmentation performance.
Results: Achieved an average IoU of 0.1813 and an average Dice score of 0.2225 on the test set.
Key Libraries Used
torch: PyTorch for deep learning model development.
torchvision: For pre-trained models and image transformations.
pandas: Data manipulation and DataFrame creation.
numpy: Numerical operations.
matplotlib, seaborn: Data visualization.
opencv-python (cv2): Image loading and processing.
scikit-learn: For data splitting utilities.
pytorch_grad_cam: For Grad-CAM visualizations.


