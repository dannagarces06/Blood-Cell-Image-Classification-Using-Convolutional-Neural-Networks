# Blood Cell Image Classification Using CNN

This project focuses on the automatic classification of microscopic blood cell images using a Convolutional Neural Network (CNN). The model was trained and evaluated using the BloodMNIST dataset, which belongs to the MedMNIST biomedical image dataset collection.

## Project Objective

The main objective of this project is to develop a CNN model capable of classifying blood cell images into eight different classes. This project demonstrates how deep learning can be applied to biomedical image analysis and can support automatic hematological image classification.

## Dataset

The dataset used in this project is **BloodMNIST**, a subdataset from MedMNIST.

Dataset information:

- Dataset name: BloodMNIST
- Source: MedMNIST
- Type of data: 2D biomedical images
- Image type: RGB microscopic blood cell images
- Image size: 28 × 28 × 3
- Total images: 17,092
- Number of classes: 8
- Task: Multi-class classification
- Official split: Train, validation, and test

Dataset source: https://medmnist.com/

## Blood Cell Classes

The dataset includes the following eight classes:

| Class Number | Class Name |
|---|---|
| 0 | Basophil |
| 1 | Eosinophil |
| 2 | Erythroblast |
| 3 | Immature granulocytes |
| 4 | Lymphocyte |
| 5 | Monocyte |
| 6 | Neutrophil |
| 7 | Platelet |

## Model Description

The model used in this project is a **custom Convolutional Neural Network** trained from scratch.

The CNN architecture includes:

- Conv2D layers for feature extraction
- Batch Normalization layers for training stability
- MaxPooling2D layers for dimensionality reduction
- Dropout layers to reduce overfitting
- Dense layers for classification
- Softmax output layer for 8-class prediction

The model was selected because CNNs are effective for image classification tasks and can learn visual features such as shape, color, borders, and texture from microscopic blood cell images.

## Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Learning rate | 0.001 |
| Loss function | Categorical Crossentropy |
| Batch size | 64 |
| Epochs | 40 |
| Input size | 28 × 28 × 3 |
| Number of classes | 8 |

## Project Pipeline

The workflow of the project follows these steps:

1. Load the BloodMNIST dataset.
2. Split the data into training, validation, and test sets.
3. Normalize image pixel values from 0–255 to 0–1.
4. Convert labels to categorical format.
5. Build the CNN architecture.
6. Train the model using the training set.
7. Validate the model using the validation set.
8. Evaluate the model using the test set.
9. Generate accuracy, loss, confusion matrix, ROC curve, and classification report.
10. Predict the class of individual blood cell images.

## Results

The CNN model achieved the following approximate results:

| Metric | Result |
|---|---|
| Accuracy | 94% |
| Precision | 94% |
| Recall | 94% |
| F1-score | 94% |
| AUC | 0.99 – 1.00 |

The confusion matrix showed that most predictions were located on the main diagonal, meaning that the model correctly classified most blood cell images.

The ROC curves showed AUC values close to 1.00 for most classes, indicating that the model had excellent ability to distinguish between blood cell categories.

## Requirements

To run this project, install the following libraries:

```bash
pip install medmnist tensorflow numpy matplotlib seaborn scikit-learn
