# Eye Disease Classification and Segmentation using Computer Vision

This project demonstrates the use of computer vision and deep learning techniques for analyzing retinal images to classify and segment eye diseases. The system includes:

1- Eye Disease Classification using a ResNet18 convolutional neural network

2- Feature Segmentation using traditional image processing (OpenCV) techniques, including vessel detection and lesion approximation


# Dataset
The dataset contains retinal fundus images categorized into four classes:

Cataract: Clouding of the lens leading to blurry vision; common in older adults.

Diabetic Retinopathy (DR): Damage to retinal blood vessels due to diabetes; can cause vision loss if untreated.

Glaucoma: Progressive damage to the optic nerve, often associated with increased intraocular pressure.

Normal: Healthy retina with no visible abnormalities.

Dataset source:  [Eye Diseases Classification Kaggle](https://www.kaggle.com/code/mahnazarjmand/eye-diseases-classification/input)


# Project Structure

## 1. Classification

Preprocessing and data augmentation (resize, random flip, rotation, color jitter, normalization)

Train/test split (80/20)

Pretrained ResNet18 fine-tuned for 4-class classification

Training using CrossEntropyLoss and Adam optimizer

Evaluation includes confusion matrix and classification report



## 2. Segmentation

### Vessel Segmentation:

* Converts RGB to grayscale

* Enhances contrast using CLAHE

* Detects vessels using Canny edge detection

### Lesion Approximation:

* Converts RGB to HSV

* Detects red regions (common in DR and other retinal lesions)

* Applies morphological operations to clean up the mask

## Feature Extraction:

* Vessel density

* Lesion area

* Color features: mean and standard deviation of RGB channels, brightness

# Results

<img width="474" height="441" alt="image" src="https://github.com/user-attachments/assets/c8b2ea06-a5c1-49fd-a24f-adbbdc3da08c" />


<img width="501" height="193" alt="image" src="https://github.com/user-attachments/assets/88cf4988-8257-4aa8-9fc1-4ec3624848c2" />


## Overall Performance:

Accuracy = 90% of all test images were classified correctly.
Loss = 0.2537,  Lower loss indicates the model’s predictions are close to the true labels.

### Interpretation

Best performing class: Diabetic Retinopathy (precision 1.0, recall 0.98)

Class needing improvement: Glaucoma (recall 0.74 → 26% of glaucoma images were misclassified)

Overall: Model is performing very well, loss is low, accuracy is ~90%, and most classes have F1 > 0.85.

# Predicted vs actual results
<img width="1260" height="668" alt="download" src="https://github.com/user-attachments/assets/0393ac74-2107-431e-97b9-f7a0631044db" />


# image segmentation of each eye disease

<img width="1077" height="341" alt="image" src="https://github.com/user-attachments/assets/c793a383-6d12-4555-9daa-3896c8420ca9" />


<img width="1059" height="334" alt="image" src="https://github.com/user-attachments/assets/a8646cf9-fdb0-4ca3-b533-5a902571e44e" />


<img width="1057" height="335" alt="image" src="https://github.com/user-attachments/assets/4758b0e6-6bf4-4ca7-96b6-d02aa48a5966" />


<img width="1052" height="332" alt="image" src="https://github.com/user-attachments/assets/df60f9c8-6b56-4b8f-ad65-20223e62d2a4" />




