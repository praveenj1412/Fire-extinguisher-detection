# Fire Extinguisher Detection

## Introduction
The objective of this project is to detect fire extinguishers in real-time using edge devices. The dataset, along with annotations, undergoes various preprocessing techniques for training. The YOLOv11 model from the YOLO framework is used for training, achieving optimal accuracy after a two-stage training process. The trained model is tested with random images and deployed for real-time detection via a camera.

---

## Tools and Technologies
- **Language:** Python
- **Libraries:** `ultralytics`, `opencv`, `roboflow`
- **Framework:** YOLO

---

## About the Dataset
The dataset, collected from the Roboflow repository, consists of:
- 5865 images with annotations.
- An additional set of 580 images with respective annotations.

---

## Preprocessing
Each image is resized to `640x640`, the optimal size for the YOLO model. Augmentations are applied to enhance the dataset:
- **Image augmentations:**
  - Horizontal flipping.
  - 90° rotations (clockwise and counter-clockwise).
  - Random rotations (-30° to +30°).
  - Blur (up to 2px).
  - Pixel noise (up to 5%).
  - Three cutout boxes (16% size each).
- **Bounding box augmentations:**
  - Horizontal flipping.
  - Smaller rotations (-15° to +15°).
  - Blur (up to 1.75px).
  - Pixel noise (up to 3%).

---

## Training
### Model 1: YOLOv11n
- The dataset is split into training, validation, and test sets.
- Paths and preprocessing steps are specified in a `data.yaml` file.
- The model is trained for **50 epochs** to achieve the best weights.

### Model 2: Fine-Tuning
- The best model from Model 1 is retrained with a small set of images.
- Fine-tuning reduces the threshold value and improves feature capture.

---

## Validation
Validation results are analyzed using:
- Training loss and validation loss.
- Mean Average Precision (mAP).
- Precision and recall.

## Deployment
The trained model is saved and deployed for real-time object detection using a webcam.

### Output from Camera:
**Video Result:** [Link to Video]([https://drive.google.com/file/d/1vnuPDUbckaBLc616Fn3f-3m1DKf8EY8A/view?usp=drive_link](https://drive.google.com/file/d/1c8kQFSusNYsHScf_s2Ib4jJws-MZ3VYh/view?usp=sharing))

---

## Installation and Usage
### Prerequisites:
- Python 3.8+
- Install dependencies using:
  ```bash
  pip install -r requirements.txt
