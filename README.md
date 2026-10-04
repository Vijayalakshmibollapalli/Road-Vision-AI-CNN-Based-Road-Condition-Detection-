# Road-Vision-AI-CNN-Based-Road-Condition-Detection

## Overview

This project focuses on detecting **road damage and potholes** using Deep Learning and Computer Vision.

The project uses a **CNN model** as a baseline and **VGG16 Transfer Learning** to classify road images into two categories:

* **Clean Road**
* **Potholes**

The trained model can also process video frames and classify the road condition in the video.

The project is being extended toward **object detection**, where potholes can be localized using bounding boxes.

---

## Dataset

The dataset contains two classes:

| Class      |  Images |
| ---------- | ------: |
| Clean Road |     370 |
| Potholes   |     480 |
| **Total**  | **850** |

## Project Workflow

```text
Dataset
   ↓
Image Preprocessing
   ↓
Train/Test Split
   ↓
Basic CNN
   ↓
Data Augmentation
   ↓
VGG16 Transfer Learning
   ↓
VGG16 Fine-Tuning
   ↓
Model Evaluation
   ↓
Image Prediction
   ↓
Video Prediction
   ↓
YOLO Object Detection
```

---

## Technologies Used

* Python
* TensorFlow
* Keras
* OpenCV
* NumPy
* Matplotlib
* Scikit-learn
* VGG16
* CNN
* Transfer Learning
* Fine-Tuning
* YOLO

---

## Data Preprocessing

The images are processed using OpenCV.

Main preprocessing steps:

1. Read images.
2. Convert BGR to RGB.
3. Resize images to `120 × 120`.
4. Normalize pixel values for CNN training.
5. Encode class labels.
6. Split the dataset into training and testing sets.

The dataset is split into:

```text
Training: 680 images
Testing: 170 images
```

---

## Models Used

### 1. Basic CNN

A custom CNN was developed using:

```text
Conv2D
↓
MaxPooling
↓
Conv2D
↓
MaxPooling
↓
Conv2D
↓
MaxPooling
↓
Flatten
↓
Dense
↓
Dropout
↓
Output
```

### Result

**Test Accuracy: 94.71%**

---

### 2. CNN with Data Augmentation

Image augmentation was applied using:

* Rotation
* Width shifting
* Height shifting
* Zoom
* Shearing
* Horizontal flipping

### Result

**Test Accuracy: 88.82%**

---

### 3. VGG16 Transfer Learning

VGG16 pretrained on ImageNet was used as a feature extractor.

Additional fully connected layers were added for road-condition classification.

### Result

**Test Accuracy: 99.41%**

---

### 4. VGG16 Fine-Tuning

The final convolutional block of VGG16 was unfrozen and trained with a small learning rate.

### Result

**Test Accuracy: 99.41%**

---

## Model Comparison

| Model                   | Accuracy |
| ----------------------- | -------: |
| Basic CNN               |   94.71% |
| CNN + Data Augmentation |   88.82% |
| VGG16 Transfer Learning |   99.41% |
| Fine-Tuned VGG16        |   99.41% |

---

## 🖼️ Image Prediction

The final VGG16 model can classify a new road image as:

```text
Clean Road
```

or

```text
Potholes
```

The prediction also provides a confidence score.

Example:

```text
Predicted Road Condition: Potholes
Confidence: 100.00%
```

---

## Video Prediction

The trained VGG16 model processes the video frame-by-frame.

For each frame, it predicts:

```text
POTHOLES
```

or

```text
CLEAN ROAD
```

The prediction is displayed on the video frame and the processed video can be saved as an output video.

---

## Future Improvements

* Pothole localization using YOLO
* Bounding-box detection
* Video-based pothole detection
* Real-time road damage detection
* Detection of multiple potholes in a single frame
* Deployment as a web or mobile application

---

## Skills Demonstrated

This project demonstrates practical experience with:

**Python | Deep Learning | CNN | VGG16 | Transfer Learning | Fine-Tuning | TensorFlow | Keras | OpenCV | Computer Vision | Image Classification | Video Processing | Object Detection**
